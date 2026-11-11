# Journey accessibility findings: tried on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the invented example in [example.md](example.md) (Client T, an invented tool-hire company). No client data was used. The run used the template's instruction block and output format, and the assistant read the example's finding list only after producing its own.

## Inputs used

The four inputs under "The inputs" in example.md: the review settings, steps.csv (5 steps), criteria.csv (6 criteria) and evidence.csv (17 rows), with the exclusion "payment on the reservation is out of scope".

## What came out

```
JOURNEY ACCESSIBILITY FINDINGS: Reserve a tool for a weekend, Client T (an invented tool-hire company)

For: Client T's design owner, with the reviewer engaged by Client T. Task: A customer finds a tool, picks pickup and return dates, enters contact details and receives a reservation number. As of 2026-11-09. Receives the list: design owner, with the accessibility reviewer.

Summary: 9 findings. Blocks the task: 3 (5, 6, 7). Hinders the task: 2 (2, 8). No effect on the task reported: 2 (3, 4). Not established: 2 (1, 9). Not yet observed by a person: 2 (1, 9).
Evidence rows: 17. Findings from 10 problem rows. Reported working: 5. Outside the agreed criteria: 1. Unclear: 1. Check: 10 + 5 + 1 + 1 = 17.
Hands-on checks: 7 of 20 done; 13 still required (7 not done, 6 to do on the built page).

THE JOURNEY STEP BY STEP

Step 1. Find a tool (Search results page, live page)
Evidence rows: E1, E2, E3, E16. Findings: 1, 2.
Hands-on checks: keyboard done (E2, E3); screen reader not done; zoom not done; contrast not done.

Step 2. Check the tool (Tool page, live page)
Evidence rows: E4, E5, E6, E7, E17. Findings: 3, 4.
Hands-on checks: keyboard done (E17); screen reader done (E4, E5); zoom not done; contrast done (E6).

Step 3. Choose dates (Date picker, built prototype)
Evidence rows: E8, E9, E10, E12, E15. Findings: 5, 6, 7, 8.
Hands-on checks: keyboard done (E8, E9, E10); screen reader not done; zoom done (E15); contrast not done.

Step 4. Enter details (Details form, static design)
Evidence rows: E11, E13. Findings: 9.
Hands-on checks: keyboard not possible on a static design; to do on the built page; screen reader not possible on a static design; to do on the built page; zoom not possible on a static design; to do on the built page; contrast done (E13).

Step 5. Confirm (Confirmation page, static design)
Evidence rows: E14. Findings: none.
Hands-on checks: keyboard not possible on a static design; to do on the built page; screen reader not possible on a static design; to do on the built page; zoom not possible on a static design; to do on the built page; contrast not done.

FINDINGS

1. Step 1, Find a tool: Filter checkboxes, criterion S1
Criterion: Controls and images have names that say what they are or do.
Evidence: E1 (automated check; Automated checker A): The checker reports 3 filter checkboxes with no accessible name.
Task impact: Not established (no row states an effect).
Evidence strength: Automated check only.
Manual check still required: screen reader, step 1, not done.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding 1 from the evidence, what change does the design owner agree, and who retests it?

2. Step 1, Find a tool: Filter panel close control, criterion K1
Criterion: Every action can be done with the keyboard alone.
Evidence: E3 (keyboard; Keyboard only; Browser A): Tab skips the Close control inside the open Filters panel. The reviewer left the panel with Escape which the screen does not mention.
Task impact: Hinders the task (from E3).
Evidence strength: Observed by a person.
Manual check still required: none beyond the reviewer's verification.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding 2 from the evidence, what change does the design owner agree, and who retests it?

3. Step 2, Check the tool: Tool photo, criterion S1
Criterion: Controls and images have names that say what they are or do.
Evidence: E4 (screen reader; Screen reader A; Browser A): The photo is announced as IMG_4471.jpg.
Task impact: No effect on the task reported (from E4).
Evidence strength: Observed by a person.
Manual check still required: none beyond the reviewer's verification.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding 3 from the evidence, what change does the design owner agree, and who retests it?

4. Step 2, Check the tool: Price text on the banner, criterion V1
Criterion: Text has the contrast the team agreed (4.5 to 1).
Evidence: E6 (contrast; Contrast tool A; Browser A): Measured 3.1 to 1 for the price text on the grey banner; the agreed ratio is 4.5 to 1.
Task impact: No effect on the task reported (from E6).
Evidence strength: Observed by a person.
Manual check still required: none beyond the reviewer's verification.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding 4 from the evidence, what change does the design owner agree, and who retests it?

5. Step 3, Choose dates: Pickup date grid, criterion K1
Criterion: Every action can be done with the keyboard alone.
Evidence: E8 (keyboard; Keyboard only; Browser A): Arrow keys do not move between days. Tab reaches the grid once as a single stop and no day can be chosen with the keyboard.
Evidence: E12 (page inspection; Prototype markup read by the reviewer): Day cells are div elements with a click handler and no key handler.
Task impact: Blocks the task (from E8).
Evidence strength: Observed by a person.
Manual check still required: none beyond the reviewer's verification.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding 5 from the evidence, what change does the design owner agree, and who retests it?

6. Step 3, Choose dates: Pickup date grid, criterion K2
Criterion: The focus mark is always visible and moves in a sensible order.
Evidence: E9 (keyboard; Keyboard only; Browser A): When Tab reaches the grid as a single stop no focus mark is visible.
Task impact: Blocks the task (from E9).
Evidence strength: Observed by a person.
Manual check still required: none beyond the reviewer's verification.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding 6 from the evidence, what change does the design owner agree, and who retests it?

7. Step 3, Choose dates: Return date grid, criterion K1
Criterion: Every action can be done with the keyboard alone.
Evidence: E10 (keyboard; Keyboard only; Browser A): Behaves as the pickup grid does: arrow keys do not move between days and no return date can be chosen with the keyboard.
Task impact: Blocks the task (from E10).
Evidence strength: Observed by a person.
Manual check still required: none beyond the reviewer's verification.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding 7 from the evidence, what change does the design owner agree, and who retests it?

8. Step 3, Choose dates: Date picker panel, criterion R1
Criterion: The page stays usable at 200 percent zoom without sideways scrolling.
Evidence: E15 (zoom; Browser A at 200 percent): The Next month control moves off screen and the panel scrolls sideways. The reviewer reached the control only by scrolling sideways.
Task impact: Hinders the task (from E15).
Evidence strength: Observed by a person.
Manual check still required: none beyond the reviewer's verification.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding 8 from the evidence, what change does the design owner agree, and who retests it?

9. Step 4, Enter details: Error message under the email field, criterion S2
Criterion: Error and status messages are announced to a screen reader.
Evidence: E11 (design file; Design file frame 4.2 read by the reviewer): The error is shown only as red text under the field. The frame specifies no announcement.
Task impact: Not established (no row states an effect).
Evidence strength: Design file only.
Manual check still required: screen reader, step 4, not possible on a static design; to do on the built page.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding 9 from the evidence, what change does the design owner agree, and who retests it?

OBSERVATIONS THAT DID NOT BECOME FINDINGS

Outside the agreed criteria: E16, step 1, Whole page, automated check: The checker reports that the page language is not set. Question: does the team add a criterion for it, or set it aside?
Unclear observations: E7, step 2, Specification table, page inspection: The table has no header cells in the markup. How a screen reader reads it has not been listened to. Question: which check settles it?
Reported working: E2, E5, E13, E14, E17.

LIMITS OF THIS REVIEW

Sources: step 1 Search results page (live page); step 2 Tool page (live page); step 3 Date picker (built prototype); step 4 Details form (static design); step 5 Confirmation page (static design).
Hands-on checks used: keyboard: Keyboard only; Browser A (6 rows); screen reader: Screen reader A; Browser A (2 rows); zoom: Browser A at 200 percent (1 row); contrast: Contrast tool A; Browser A (1 row) and Contrast tool A; design file values (1 row). Nothing else was run.
Steps that exist only as static designs: 4, 5. Their keyboard, screen-reader and zoom behaviour has not been checked.
Findings not yet observed by a person: 1, 9.
Criteria with no evidence of any kind: none.
Exclusions supplied: payment on the reservation is out of scope for this review.
This is a list of findings for the reviewer to verify. It states no conformance, rates no standard and declares no step of Reserve a tool for a weekend accessible.

Every statement traces to the evidence rows and files supplied, as of 2026-11-09. The review changes no page, design file or record and sends nothing; the accessibility reviewer verifies each finding, and the design owner and reviewer agree any fix.
```

## What was observed

- **Every required part was produced.** The summary, the step-by-step section, nine findings, the three groups of observations that did not become findings, and the limits all came out. The four counts added up (10 + 5 + 1 + 1 = 17). No stop condition applied, because the inputs were clean.
- **Agreement with the published example.** The finding count, numbering, task-impact labels, evidence-strength labels, hands-on check totals (7 of 20 done; 13 still required) and the groups of observations match. My first count of done checks was 8, a slip of mine in adding up step 3 (it has two checks done, not three), caught by recounting each step; the template's rule is clear and gives 7.
- **Differences from the published example, all in wording and layout, none in substance:**
  - Title line: I added "(an invented tool-hire company)" after Client T; the example has just "Client T".
  - "For:" line: I wrote "the reviewer engaged by Client T" as the reviewer, copying the review settings; the example says "the accessibility reviewer".
  - "Manual check still required": I wrote "screen reader, step 1, not done"; the example writes "screen reader at step 1: not done".
  - Finding 5 has two evidence rows. I gave each its own "Evidence:" line; the example runs them together in one line.
  - "Sources": I listed each step by name and page with its source type; the example groups them ("steps 1 and 2 live pages; ...").
- **Where the template was ambiguous and I had to choose:**
  - How to write the manual-check line: the template gives the content (check, step, status) but not the punctuation.
  - Whether several evidence rows in one finding go on one line or separate lines. The format says "one entry for each row" and does not say which.
  - The form of the "Sources" line: the template says "step list with source type", which allows either layout.
  - The title line has "[journey], [product or organization]". The settings give a client, not a product, so I used the client name and its description.
  - Whether the reviewer's name should be copied from the review settings (a phrase, not a name) or called "accessibility reviewer". I copied it.
  - A contrast measurement taken on design-file values (E13) counts as a done contrast check under the rule "whatever its result", and appears in the limits as a contrast method. That follows the text, but a reviewer may not expect a design-file measurement to count as hands-on.
  - The template does not say what status a contrast check has on a static design with no contrast row (step 5). By the rule it is "not done"; the example agrees.
- **Nothing in either output is missing from the inputs.** Every statement in my output and in the example's traces to the review settings and the step, criteria and evidence rows. The example's output adds no fact of its own.
- **Limits of this trial.** One run, by one model, on one invented example. It shows the instructions can be followed to the published result; it does not show how the template performs on a real journey, and it says nothing about conformance with any standard.

## Changes to the template after this run

After this run the template was edited, and this record was not re-run or altered. The edits pinned the three layout choices listed above to the published example's forms (the manual-check line written "[check] at step [k]: [status]", all of a finding's evidence entries on one line, and the Sources line grouped by source type), changed the status text for a static design to use a comma ("not possible on a static design, to do on the built page") so the semicolons between checks read clearly, and removed a clause from procedure step 8 that contradicted the rule before it. The output above therefore shows the earlier wording of those lines. The example's "For:" line was also changed afterwards to copy the review settings ("the reviewer engaged by Client T"), as this run did, so the difference noted above under "Differences from the published example" no longer exists. The template now also says to write the client's name only in the title (this run added a description) and how several unclear or outside-criteria rows are laid out, and the instruction block names an evidence row with an unknown step; the output above shows the earlier wording. No figure was affected. A new run on the revised template has not been made.
