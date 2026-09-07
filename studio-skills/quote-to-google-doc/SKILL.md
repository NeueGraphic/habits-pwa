---
name: quote-to-google-doc
description: "Takes a Neue Graphic Studio proposal (from proposal-generator or questionnaire-to-plan-and-quote, or provided directly) and publishes it as a formatted Google Doc ready to share with the client, preserving the fixed eight-section structure. Trigger whenever the user wants to turn a proposal, plan or quote into a Google Doc, or says things like 'put this in a Google Doc', 'make this a shareable doc', 'send this to the client as a doc', 'create a Google Doc from this quote', 'turn this into a doc', or 'make this shareable'. Also trigger immediately after running proposal-generator or questionnaire-to-plan-and-quote if the user says 'now make it a doc' or similar. Works from the raw proposal text — no extra input needed."
---

# Quote to Google Doc

Takes a Neue Graphic Studio proposal and publishes it as a polished, client-ready Google Doc.

---

## The Rule

**The doc is eight sections. Nothing else earns a spot.**

1. The goal of the project
2. The format
3. What's included
4. How the support works
5. What it looks like at the outcome
6. The timeframe
7. The investment
8. What to do next

Do not add a cover page, table of contents, studio background, credentials, appendix, or terms page. The title block and signature block are document furniture, not sections.

If the source content is missing a section, write the heading and one line marking it as pending client confirmation rather than dropping it. If the source content carries something outside the eight — an assumptions preamble, a philosophy note, a case study — fold it into the section it belongs to, or leave it out. Tell the user what you folded or dropped.

---

## What This Skill Produces

A Google Doc with:
- Neue Graphic Studio title block
- Eight numbered section headings, in order
- A formatted table for the investment line items
- A signature block
- A shareable link the user can copy and send directly to the client

---

## Step 1: Gather the Content

If the proposal is already in the current conversation, use it directly. If not, ask the user to paste it in.

Identify and extract:
- **Document title** — derive from client name or project name if visible (e.g. "Project Proposal — [Client Name]")
- **Each of the eight sections** — map the source content onto the structure above, even if the source used different headings

Common remaps from older proposal formats:

| Source heading | Goes to |
|---|---|
| Introduction / cover letter | Fold the substance into 1, or drop |
| Project Overview | 1. The goal of the project |
| Scope of Work / Plan of Action | 2. The format (sequence) and 3. What's included (deliverables) |
| Deliverables | 3. What's included |
| What's Not Included / Exclusions | Tail of 3. What's included |
| How We Work / Quote notes | 4. How the support works |
| Handover / Outcome | 5. What it looks like at the outcome |
| Timeline | 6. The timeframe |
| Service Quote / Investment / Terms | 7. The investment |
| Next Steps | 8. What to do next |

---

## Step 2: Choose the Execution Path

The right approach depends on what tools are active in the current session. Check in this order:

### Path A — Claude in Chrome (preferred, fully automated)
If `Claude in Chrome` tools are available, use browser automation to create and populate the doc:

1. Navigate to `https://docs.google.com/document/create`
2. Wait for the blank doc to load
3. Rename the document using the title field (click the "Untitled document" area top-left)
4. Type/paste content using keyboard input — structure it as per Step 3 below
5. Apply headings using Format > Paragraph styles (or keyboard shortcuts: Cmd+Alt+1 for H1, Cmd+Alt+2 for H2)
6. Insert the investment table via Insert > Table
7. Copy the URL from the browser address bar and return it to the user

**Keyboard shortcuts in Google Docs (use these for speed):**
- Heading 1: `Cmd+Alt+1`
- Heading 2: `Cmd+Alt+2`
- Normal text: `Cmd+Alt+0`
- Bold: `Cmd+B`
- New line: `Enter`
- Tab (in tables): `Tab`

### Path B — Google Drive MCP (creates doc, no rich formatting)
If `google_drive_search` / `google_drive_fetch` tools are available but Chrome is not:
- The Drive MCP is read-only — it cannot create new documents
- Skip to Path C

### Path C — Paste-ready fallback (always works)
If neither Chrome nor a write-capable Drive tool is available:
1. Produce the complete doc content as clean Markdown, eight sections in order
2. Tell the user to go to `docs.google.com`, create a new doc, and paste it in
3. Provide a one-paragraph formatting guide (select section headings → Heading 1, etc.)

---

## Step 3: Document Structure & Formatting

Build the doc in this exact order:

### Title block (at top)
```
[Client Name] — Project Proposal          ← Title style (or largest text)
Prepared by Neue Graphic Studio           ← Subtitle or Normal
[Date: e.g. April 2026]                   ← Normal
```

Add a blank line after the title block. No cover page, no logo lockup, no contents list.

### The eight sections

Each heading is numbered and set as Heading 1. Body copy is Normal.

```
1. The goal of the project        ← Heading 1
[one paragraph]

2. The format                     ← Heading 1
[short prose or phase list]

3. What's included                ← Heading 1
Phase 01 — [Title]                ← Heading 2 (only if phased)
[bulleted deliverables]

Not included                      ← Heading 2
[3–5 bullets]

4. How the support works          ← Heading 1
[prose plus working terms]

5. What it looks like at the outcome   ← Heading 1
[one paragraph]

6. The timeframe                  ← Heading 1
[total, then one line per phase]

7. The investment                 ← Heading 1
[Table — 3 columns]
| Phase | Scope | Investment |
| Phase 01... | ... | $X,XXX |
| Total | | $XX,XXX + GST |     ← bold row

[two lines: deposit / balance]

8. What to do next                ← Heading 1
[numbered list, 3–4 steps]
```

### Signature block (at bottom)
```
Cam
Director, Neue Graphic Studio
cam@neuegraphic.com.au
neuegraphic.com.au
```

---

## Step 4: Sharing Note

**Do not attempt to change sharing permissions.** This is a prohibited action.

After the doc is created, always tell the user:

> "Your Google Doc is ready at [URL]. To send it to the client: open the doc, click Share (top right), set to 'Anyone with the link can view', and copy the link — or add their email directly."

---

## Tone & Presentation

Keep it clean — this doc represents Neue Graphic to the client:
- No decorative elements or colour
- Clear heading hierarchy, eight headings only
- Investment table is the only table in the document — ensure all columns are legible
- White space between sections
- One page of content per section at most; the whole document should read in a few minutes

---

## Error Handling

| Situation | Response |
|---|---|
| No proposal content in conversation | Ask user to paste the output from proposal-generator or questionnaire-to-plan-and-quote |
| Source content is missing a section | Write the heading with a one-line "to be confirmed" note; tell the user which sections were thin |
| Source content has extra sections | Fold into the nearest of the eight, or drop; tell the user what you did |
| Chrome tools unavailable | Fall back to Path C (paste-ready Markdown) |
| Google Docs fails to load | Try again; if persistent, deliver Path C output |
| Client name not found | Use "Project Proposal" as doc title; note this to user |
| Table formatting fails | Create the table manually row by row using Tab to move between cells |

---

## Output to User

Always end with one of these:

**If doc was created:**
```
✓ Google Doc created: [URL]

To share with [Client Name]: open the link, click Share, set to "Anyone with the link can view" and copy — or add their email directly.
```

**If paste fallback:**
```
I wasn't able to create the doc directly. Here's your content ready to paste into a new Google Doc:

[formatted Markdown content]

Go to docs.google.com → New → Blank document, paste this in, then:
- Select each of the eight section headings → Format > Paragraph styles > Heading 1
- The investment table will need to be inserted via Insert > Table (3 columns)
```
