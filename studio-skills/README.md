# Studio skills — proposal set

Source of truth for the three Neue Graphic Studio skills that produce client
proposals. These are versioned here so changes are reviewable; the live copies
run from the Claude skill settings and must be updated there to take effect.

## The eight-section rule

Every proposal Neue Graphic sends is eight sections, in this order:

1. The goal of the project
2. The format
3. What's included
4. How the support works
5. What it looks like at the outcome
6. The timeframe
7. The investment
8. What to do next

Nothing else earns a spot. No cover letter, no studio background, no
credentials, no appendix. The order is fixed so value is established before
price.

Two things that used to be their own sections now live inside others:

- Exclusions sit at the tail of **3. What's included**
- Terms (revisions, IP transfer, feedback) sit in **4. How the support works**;
  payment structure sits in **7. The investment**

Header and signature blocks are document furniture, not sections.

## Files

| Skill | Role |
|---|---|
| `proposal-generator/` | Writes the proposal from a brief or conversation |
| `questionnaire-to-plan-and-quote/` | Writes the proposal from a completed client questionnaire |
| `quote-to-google-doc/` | Publishes a proposal as a formatted Google Doc |

All three carry the same eight-section structure so a proposal keeps its shape
from draft through to the doc the client opens.

## Applying an update

Paste the changed `SKILL.md` into the matching skill at
claude.ai → Settings → Capabilities → Skills. Editing a local synced copy does
not persist.
