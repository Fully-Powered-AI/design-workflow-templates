# Journey accessibility findings: an invented example

*Illustrative example with invented data.* Client T is an invented regional tool-hire company, and its website, the journey, the design files, the software named only by letter, the roles and every observation below are invented. The accessibility reviewer walked one journey, reserving a tool for a weekend, and wrote down what was seen. The assistant organized those notes into the finding list. Nothing here describes a real product or a real review.

## The inputs

### 1. Review settings

```
Client: Client T (an invented tool-hire company)
Journey: Reserve a tool for a weekend
Task: A customer finds a tool, picks pickup and return dates, enters contact details and receives a reservation number.
As-of date: 2026-11-09
Accessibility reviewer: the reviewer engaged by Client T
Design owner: Client T's design owner
Report goes to: design owner, with the accessibility reviewer
Exclusions: payment on the reservation is out of scope for this review
```

### 2. Journey steps (steps.csv)

```
step_no,step_name,page_or_screen,source_type,user_action
1,Find a tool,Search results page,live page,Searches for a tool and opens a result
2,Check the tool,Tool page,live page,Reads the details and chooses Reserve
3,Choose dates,Date picker,built prototype,Picks a pickup date and a return date
4,Enter details,Details form,static design,Enters name email and phone and submits
5,Confirm,Confirmation page,static design,Reads the reservation number
```

### 3. Agreed criteria (criteria.csv)

```
criterion_id,criterion,checked_by
K1,Every action can be done with the keyboard alone,keyboard
K2,The focus mark is always visible and moves in a sensible order,keyboard
S1,Controls and images have names that say what they are or do,screen reader
S2,Error and status messages are announced to a screen reader,screen reader
V1,Text has the contrast the team agreed (4.5 to 1),contrast
R1,The page stays usable at 200 percent zoom without sideways scrolling,zoom
```

### 4. Evidence (evidence.csv)

```
evidence_id,step_no,kind,element,observed_with,criterion_id,result,task_effect,observation
E1,1,automated check,Filter checkboxes,Automated checker A,S1,problem,not stated,The checker reports 3 filter checkboxes with no accessible name.
E2,1,keyboard,Results list,Keyboard only; Browser A,K1,works,none,Reached all 12 results with Tab and opened one with Enter.
E3,1,keyboard,Filter panel close control,Keyboard only; Browser A,K1,problem,hinders,Tab skips the Close control inside the open Filters panel. The reviewer left the panel with Escape which the screen does not mention.
E4,2,screen reader,Tool photo,Screen reader A; Browser A,S1,problem,none,The photo is announced as IMG_4471.jpg.
E5,2,screen reader,Reserve button,Screen reader A; Browser A,S1,works,none,Announced as Reserve this tool; button.
E6,2,contrast,Price text on the banner,Contrast tool A; Browser A,V1,problem,none,Measured 3.1 to 1 for the price text on the grey banner; the agreed ratio is 4.5 to 1.
E7,2,page inspection,Specification table,Page markup read by the reviewer,,unclear,not stated,The table has no header cells in the markup. How a screen reader reads it has not been listened to.
E8,3,keyboard,Pickup date grid,Keyboard only; Browser A,K1,problem,blocks,Arrow keys do not move between days. Tab reaches the grid once as a single stop and no day can be chosen with the keyboard.
E9,3,keyboard,Pickup date grid,Keyboard only; Browser A,K2,problem,blocks,When Tab reaches the grid as a single stop no focus mark is visible.
E10,3,keyboard,Return date grid,Keyboard only; Browser A,K1,problem,blocks,Behaves as the pickup grid does: arrow keys do not move between days and no return date can be chosen with the keyboard.
E11,4,design file,Error message under the email field,Design file frame 4.2 read by the reviewer,S2,problem,not stated,The error is shown only as red text under the field. The frame specifies no announcement.
E12,3,page inspection,Pickup date grid,Prototype markup read by the reviewer,K1,problem,not stated,Day cells are div elements with a click handler and no key handler.
E13,4,contrast,Phone field label,Contrast tool A; design file values,V1,works,none,Label text measures 7.2 to 1.
E14,5,design file,Reservation number,Design file frame 5.1 read by the reviewer,S1,works,none,The number is live text and not an image.
E15,3,zoom,Date picker panel,Browser A at 200 percent,R1,problem,hinders,The Next month control moves off screen and the panel scrolls sideways. The reviewer reached the control only by scrolling sideways.
E16,1,automated check,Whole page,Automated checker A,,problem,not stated,The checker reports that the page language is not set.
E17,2,keyboard,Reserve button,Keyboard only; Browser A,K1,works,none,Reached with Tab and activated with Enter.
```

## The finding list

```
JOURNEY ACCESSIBILITY FINDINGS: Reserve a tool for a weekend, Client T

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
Hands-on checks: keyboard not possible on a static design, to do on the built page; screen reader not possible on a static design, to do on the built page; zoom not possible on a static design, to do on the built page; contrast done (E13).

Step 5. Confirm (Confirmation page, static design)
Evidence rows: E14. Findings: none.
Hands-on checks: keyboard not possible on a static design, to do on the built page; screen reader not possible on a static design, to do on the built page; zoom not possible on a static design, to do on the built page; contrast not done.

FINDINGS

1. Step 1, Find a tool: Filter checkboxes, criterion S1
Criterion: Controls and images have names that say what they are or do.
Evidence: E1 (automated check; Automated checker A): The checker reports 3 filter checkboxes with no accessible name.
Task impact: Not established (no row states an effect).
Evidence strength: Automated check only.
Manual check still required: screen reader at step 1: not done.
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
Evidence: E8 (keyboard; Keyboard only; Browser A): Arrow keys do not move between days. Tab reaches the grid once as a single stop and no day can be chosen with the keyboard. E12 (page inspection; Prototype markup read by the reviewer): Day cells are div elements with a click handler and no key handler.
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
Manual check still required: screen reader at step 4: not possible on a static design, to do on the built page.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding 9 from the evidence, what change does the design owner agree, and who retests it?

OBSERVATIONS THAT DID NOT BECOME FINDINGS

Outside the agreed criteria: E16, step 1, Whole page, automated check: The checker reports that the page language is not set. Question: does the team add a criterion for it, or set it aside?
Unclear observations: E7, step 2, Specification table, page inspection: The table has no header cells in the markup. How a screen reader reads it has not been listened to. Question: which check settles it?
Reported working: E2, E5, E13, E14, E17.

LIMITS OF THIS REVIEW

Sources: steps 1 and 2 live pages; step 3 built prototype; steps 4 and 5 static designs.
Hands-on checks used: keyboard: Keyboard only; Browser A (6 rows); screen reader: Screen reader A; Browser A (2 rows); zoom: Browser A at 200 percent (1 row); contrast: Contrast tool A; Browser A (1 row) and Contrast tool A; design file values (1 row). Nothing else was run.
Steps that exist only as static designs: 4, 5. Their keyboard, screen-reader and zoom behaviour has not been checked.
Findings not yet observed by a person: 1, 9.
Criteria with no evidence of any kind: none.
Exclusions supplied: payment on the reservation is out of scope for this review.
This is a list of findings for the reviewer to verify. It states no conformance, rates no standard and declares no step of Reserve a tool for a weekend accessible.

Every statement traces to the evidence rows and files supplied, as of 2026-11-09. The review changes no page, design file or record and sends nothing; the accessibility reviewer verifies each finding, and the design owner and reviewer agree any fix.
```
