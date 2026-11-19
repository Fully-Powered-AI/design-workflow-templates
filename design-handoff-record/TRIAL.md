# Trial: Design handoff record, run on its example

- **Product:** Claude, run in Claude Code

Model: Claude Sonnet 5.5 (model ID claude-sonnet-5-5). The assistant that ran this trial did not write the template.

Date: 2026-11-10

The inputs are the example in `public/example.md` (Quillon Parcels, a made-up parcel-tracking company). No client data was used.

## History of this record

The template was first run earlier on 10 November 2026. That run found five places where the instructions left the layout open and one place where the set-aside questions had no fixed wording. After the independent review the instruction block and output format were revised to settle them, so this is a second run, of the revised template, and it replaces the record of the first. The second run was made by an assistant that had already read the example's record and the first run's notes, so it shows that the revised instructions are followed as written and that nothing in them contradicts the example. It is weaker evidence than the first run, which was made blind.

## Inputs used

The settings, the eight inventory rows, the three component references, the six tokens, the two content rules and the two interaction decisions from the "What the person supplies" section of `public/example.md`.

## What came out

The revised instruction block and output format were followed as written. This is the whole output.

```
DESIGN HANDOFF RECORD: Quillon Parcels customer web app, Track a parcel version 3

For: the design owner and the engineer. Prepared: 2026-11-10, from 8 inventory rows, 3 component references, 6 tokens, 2 content rules, 2 interaction decisions and the settings.
Column check: all headers matched.
Items: 3 on 1 screen(s). Required states: 13 covered, 2 unstated. Questions: 7. Set aside: 2.

ITEMS

Track a parcel
D1 Tracking field (Field); component reference: Design library Text field.
  default: shown at 1280, "Label above a single-line input"; shown at 390, "Same field at full width"
  hover: component library only (Design library Text field)
  focus: component library only (Design library Text field)
  disabled: Q1
  error: shown at 1280, "Red outline and the message We cannot find that number under the input"
  Also shown: none.
  Tokens: color.text.default = #1F2933; space.4 = 16px; color.text.error = #B42318.
D2 Track button (Control); component reference: Design library Button.
  default: shown at 1280, "Filled button labelled Track beside the field"
  hover: component library only (Design library Button)
  focus: component library only (Design library Button)
  pressed: component library only (Design library Button)
  disabled: shown at 1280, "Grey button while the field is empty"
  loading: component library only (Design library Button)
  Also shown: none.
  Tokens: color.action.primary = #1456C8; space.5: Q2; color.action.disabled = #C9CED6.
D3 Delivery timeline (Data); component reference: Design library Timeline.
  default: shown at 1280, "Up to five events newest first with a note under each"; shown at 390, "Events stack with the date above the status"
  loading: component library only (Design library Timeline)
  empty: component library only (Design library Timeline)
  error: Q3
  Also shown: none.
  Tokens: space.6 = 24px; color.text.default = #1F2933.

RESPONSIVE BEHAVIOUR

Breakpoints: Small from 360 to 767; Medium from 768 to 1199; Large from 1200. Smallest supported width: 360.
Track a parcel, Small (360 to 767 px): D1, D3 at 390
Track a parcel, Medium (768 to 1199 px): Q4
Track a parcel, Large (1200 px and over): D1, D2, D3 at 1280

CONTENT RULES

Tracking number (on D1): rule R1: longest 24; when longer scroll within the field; format letters and digits only.
Carrier note (on D3): rule R2: longest Q5; when longer wrap; format no format stated.
Status label (on D3): no content rule. Q6.

INTERACTIONS

D1 Tracking field: Q7
D2 Track button: I1: Tap Track with a number entered -> The delivery timeline for that number appears.

QUESTIONS FOR THE DESIGN OWNER

Q1 D1 Tracking field: No disabled state is shown in the design or documented for Tracking field. What does it look like, and when does it appear?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q2 D2 Track button: The token space.5 is named for D2 but is not in the token list. Which token or value is meant?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q3 D3 Delivery timeline: No error state is shown in the design or documented for Delivery timeline. What does it look like, and when does it appear?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q4 Track a parcel, Medium: The design shows no layout for Track a parcel between 768 and 1199 px. What should the screen do there?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q5 Carrier note: Content rule R2 gives no longest value for Carrier note. What is the longest value that can occur?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q6 Status label: No content rule exists for Status label. What is the longest value that can occur, and what happens when a value is longer than the design shows?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q7 D1 Tracking field: No interaction decision is supplied for D1. What happens when the person uses it?
  Status: Open. Answer: ______ Answered by: ______ Date: ______

SET ASIDE

Inventory row D3 default at 320: the width is below the smallest supported width of 360, so the row takes no part. Is 320 to be supported? If so, the smallest supported width in the settings changes and the record is run again.
Interaction decision I2: it names D9, which is not in the design inventory. Which item is meant?

SIGN-OFF

Design owner: has answered every question and approves this record: ______ Date: ______
Engineer: confirms all 7 questions are resolved and every set-aside line is dealt with: ______ Date: ______

Draft for the design owner. No design has been created or changed, no behaviour has been assumed, and nothing has been sent.
```

## What was observed

- Every required part was produced: the header and counts, the items with states and tokens, the responsive ranges, the content rules, the interactions, the questions, the set-aside lines and the sign-off. The counts add up: 15 required states, 13 covered, 2 unstated.
- Nothing made the assistant stop. All headers matched, no value was outside its list and nothing repeated. No one asked it to fill a gap, so the decline rules were not exercised.
- Each point the first run found open was settled by the revised wording and read the same way here: the header counts the 8 rows supplied; `screen(s)` prints literally; the responsive lines list each width once with its item ids ("D1, D3 at 390"); the Interactions section has no line for the Data item D3, which has no decision; the breakpoint question is labelled with the screen and range, and the content questions with the field; and both set-aside questions come from the fixed list.
- The output is the same, line for line, as the record in `public/example.md`. No fact appears in it that is not in the inputs.

## Shortcomings

- Breakpoint coverage is checked per screen, not per item. In the Small range the record lists only D1 and D3 at 390; the Track button D2 has no row there and no question is raised. This is how the procedure is written, not a slip in the run.
- After this run the instruction block was tightened to state details the procedure already contained (case-insensitive matching, state order, the stop message, extra columns, coverage per screen). The output format and the example inputs did not change, and the block was not re-run after that wording change.
- This run was not blind (see the history above), and it exercised only the example. The decline rules, the stop conditions and the optional-file paths (no component references, no token list, no content rules, no interaction decisions) have not been run.
- The wording for a content rule that matches no field (a set-aside reason with no question) did not arise in this example.
