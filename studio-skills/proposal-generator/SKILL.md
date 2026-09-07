---
name: proposal-generator
description: "Generates a complete, client-ready project proposal for Neue Graphic Studio. Trigger whenever the user wants to write a proposal, quote a project, or put together a scope of work for a client. Also trigger for phrases like 'put together a proposal for', 'quote this project', 'write up a scope for', 'how much should I charge for', or 'proposal for [client name]'. Generates a proposal in Neue Graphic's voice - confident, premium, no filler - built on a fixed eight-section structure: the goal, the format, what's included, how the support works, the outcome, the timeframe, the investment, what to do next. Works from minimal input; make intelligent assumptions based on project type where details are missing."
---

# Proposal Generator Skill

Generates client-ready project proposals for Neue Graphic Studio — a Melbourne-based brand identity and design practice with a Swiss/modernist aesthetic serving premium clients in property, real estate, and professional services.

## The Rule

**Every proposal is eight sections. Nothing else earns a spot.**

1. The goal of the project
2. The format
3. What's included
4. How the support works
5. What it looks like at the outcome
6. The timeframe
7. The investment
8. What to do next

No cover letter. No introduction section. No "about the studio". No case studies, credentials, philosophy, or mood boards. No terms appendix. If a piece of information matters, it lives inside one of the eight sections or it doesn't go in the document.

The order is fixed. Value is established before price — the client should understand the goal, the shape of the work, and the outcome before they reach the investment figure.

## Studio Context

**Pricing tiers (use as defaults unless told otherwise):**
- Brand identity only: $4,000 – $6,000
- Brand identity + website: $8,000 – $10,000
- Brand identity + website + campaign/collateral: $10,000 – $14,000
- Day rate (Hoyne contract work): not included in client proposals

**Standard deliverables by project type:**

*Brand Identity*
- Brand strategy and positioning workshop (or intake)
- Logo system (primary, secondary, submark)
- Colour palette
- Typography system
- Brand guidelines document
- File handover pack (print and digital)

*Website (added to brand identity)*
- Sitemap and content structure
- UX wireframes
- Visual design (up to X pages, stated in proposal)
- Responsive design
- Development handover or build (state if build is included)

**Standard terms:**
- 50% deposit to commence, 50% on completion
- 2 rounds of revisions included per phase
- Additional revisions billed at $150/hr
- Intellectual property transfers on final payment
- Timeline begins on receipt of deposit and signed proposal

These terms are not a section of their own. Payment structure sits in **The investment**. Revision rounds and IP transfer sit in **How the support works**.

## Input Handling

Extract the following from the user's message or conversation context:
- Client name
- Project type (brand identity / brand + website / other)
- Any known details: industry, audience, project goals, timeline pressure
- Budget (if mentioned)
- Any specific inclusions or exclusions

If client name is missing, use "[Client Name]" as a placeholder and flag it. Make intelligent assumptions for everything else based on project type. Do not ask multiple questions — if one critical thing is missing, ask just that. Otherwise proceed.

## Output: Project Proposal

Tone: professional, warm, and direct. Write as Cam / Neue Graphic Studio in first person. No filler, no corporate boilerplate. It should feel handcrafted, not templated.

---

### Header

Document furniture, not a section. Keep it to four lines.

```
Neue Graphic Studio
Project Proposal

Prepared for: [Client Name]
Project: [Project Type]
Date: [Today's date]
```

---

### 1. The goal of the project

One short paragraph. State what this project is for in the client's terms — the business outcome, not the design activity. Reflect their situation and language back to them so it's obvious you listened.

Answer: *what changes for this client when the work is done?*

Do not open with pleasantries, gratitude, or a preamble about the studio. The first line of the proposal is the goal.

---

### 2. The format

Two to four sentences, or a short phase list. Describe the shape of the engagement — how the work is structured and delivered:

- The phases and their sequence (e.g. Discovery & Strategy → Identity Design → Guidelines & Handover)
- How work is presented (structured presentations at each milestone, not drip-fed)
- Where it happens (remote, in-person workshop, hybrid)
- Who's doing it (Cam, direct — no account layer)

This is the *container* for the work. What goes inside it is section 3.

---

### 3. What's included

The deliverables, listed plainly. Group under phase headings where the project has distinct phases; a flat bulleted list is fine for smaller engagements. Every line should be a thing the client receives, not a thing you do.

Close this section with a short **Not included** list — three to five lines, no more:

- Copywriting (unless stated)
- Photography or image licensing
- Print production management
- Website development (if design-only engagement)

Exclusions belong here, inside what's included. They are not a ninth section.

---

### 4. How the support works

Two to four sentences plus the working terms. Cover:

- Feedback: consolidated per round, 2 rounds of revisions included per phase
- Additional revisions billed at $150/hr
- Direct line to Cam throughout — no account manager
- Response expectations and how the project stays on schedule
- IP transfers on final payment

This is the section that protects the project. Keep it warm but unambiguous.

---

### 5. What it looks like at the outcome

One paragraph. Describe the end state concretely — what the client actually has in hand on the last day, and what they can now do that they couldn't before.

Be specific and physical: a complete identity system, a guidelines document their team can work from, packaged files for print and digital, a website their audience can use. Then one line on the effect: what this lets them do next.

Answer: *what does the finish line look like from where the client is standing?*

This is not a repeat of section 3. Section 3 is the list. This is the picture.

---

### 6. The timeframe

State estimated duration from deposit to delivery. Be realistic.

- Brand identity only: 4–6 weeks
- Brand + website: 8–12 weeks

Give the total, then a one-line-per-phase breakdown if the project has phases. Close with a single line noting the timeline assumes feedback returned within the agreed windows, and that it begins on receipt of deposit and signed proposal.

---

### 7. The investment

State the fee clearly and without apology. Format as:

> **Total Investment: $X,XXX + GST**
> 50% deposit ($X,XXX) to commence
> 50% balance ($X,XXX) on completion

If the project sits in a range, present a single figure or a tight range (e.g. "$5,500 – $6,000") — never a wide range that signals uncertainty. One line maximum of context around the figure. Do not justify the price; sections 1 to 6 have already done that.

---

### 8. What to do next

A numbered list, three or four steps, each one an action with a clear owner.

1. Review this proposal and come back to me with any questions
2. Confirm by email or signed return
3. I'll issue the deposit invoice on confirmation
4. Kick-off scheduled within [X] days of deposit receipt

End on the action, not on a thank you.

---

### Signature Block

Document furniture, not a section.

```
Cam [Last name if known]
Director, Neue Graphic Studio
cam@neuegraphic.com.au
neuegraphic.com.au
```

---

## Quality Check Before Outputting

1. Are there exactly eight sections, in the correct order, with no extras?
2. Does section 1 lead with the client's goal rather than a greeting?
3. Is the scope specific enough that the client knows exactly what they're getting?
4. Does section 5 paint the outcome rather than re-list the deliverables?
5. Is the investment figure presented with confidence and without justification?
6. Would Cam be comfortable sending this without editing more than a sentence or two?

If no to any of these, revise before outputting.

## Formatting Notes

- Use `###` for the eight section headings, numbered: `### 1. The goal of the project`
- Deliverables and exclusions: bullet points
- Next steps: numbered list
- Everything else: prose
- No filler phrases, no excessive hedging
- Total length: 500–700 words (not including header/signature)
- Plain document. No decorative rules, no colour, no pull quotes beyond the investment figure
