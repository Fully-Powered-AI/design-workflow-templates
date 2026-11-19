# User research plan: an example

*Illustrative example with sample data.* The product, the groups, the evidence, the permissions and every figure below are illustrative. Product Q is an illustrative meal-planning app. The research lead ran the workflow template a few weeks before a design review. First come the inputs the research lead supplied, in full, then the plan the workflow template returned.

## The inputs

### 1. The design question

```
Should the weekly plan screen open in a list view instead of a calendar grid on phones, in the redesign going to design review on 2026-12-04?
```

### 2. What the team needs to know

```
Q1: How do subscribers use the plan screen on a phone today, and how often do they switch between grid and list?
Q2: Why do some subscribers switch views, or give up looking for a given dinner?
Q3: Can a person find a given evening's dinner and swap it for another, in each view, on the redesigned screen?
```

### 3. User groups

```
group_id | who they are | how they can be reached | records held | approx size | must have | must not have
G1 | Active subscribers who plan for several people | email list of active subscribers | yes | 4200 | Opens the plan on a phone at least weekly; Plans dinners for 3 or more people |
G2 | Former subscribers | email list of subscribers who cancelled in the last 90 days | no | 310 | Cancelled in the last 90 days |
```

### 4. Existing evidence

```
evidence_id | what it is | date | groups covered | covers | self-selected
E1 | Product analytics: plan-screen views by device and view type | 2026-08-20 | G1 | Q1 | no
E2 | 14 support tickets that mention finding a dinner on the plan screen | 2026-09-30 | G1 | Q2 | yes
E3 | Interview round with 6 subscribers on meal-planning habits | 2025-01-14 | G1 | Q2 | no
```

### 5. Permissions

```
permission_id | group | status | who decides | date | note
PM1 | G1 | granted | Head of Customer Care | 2026-10-30 | email invitations to active subscribers
PM1 | G2 | not granted | Head of Customer Care | | asked, no answer yet
PM2 | | granted | Research lead | 2026-10-28 | consent text for sessions exists
PM3 | | not stated | | |
PM4 | G1 | granted | Data owner | 2026-10-28 | product analytics events for active subscribers
PM5 | | not stated | | |
PM6 | | not granted | Head of Product | | no incentive budget approved
PM7 | | granted | Product owner | 2026-11-06 | prototype build of the plan screen
```

### 6. Settings

```
research lead: Research lead
today: 2026-11-10
decision date: 2026-12-04
researcher days available: 7
recording: undecided
incentive: undecided
```

## The plan

```
USER RESEARCH PLAN: Default view of the plan screen on phones

For: Research lead. Decision: Should the weekly plan screen open in a list view instead of a calendar grid on phones, in the redesign going to design review on 2026-12-04? To be taken 2026-12-04.
Prepared: 2026-11-10, from the design question, 3 questions (supplied), 2 groups, 3 pieces of evidence, 8 permission lines, 6 settings. Not supplied: records period.
Defaults used: evidence old after 12 months, cutoff 2025-11-10 (default); 6 hours to a day, shown to the next half day (default); counts rather than percentages under 20 participants (default); survey response rate 15% (default); 5 participants per group for interviews and usability sessions (default); standing exclusions X1 and X2 (default)

WHAT WE NEED TO KNOW
Q1 How do subscribers use the plan screen on a phone today, and how often do they switch between grid and list? | type A: what people do and how often
Q2 Why do some subscribers switch views, or give up looking for a given dinner? | type B: why, and in what situation
Q3 Can a person find a given evening's dinner and swap it for another, in each view, on the redesigned screen? | type C: whether people can finish a task with a given design
Set aside: None

WHAT WE ALREADY HAVE
Q1: partly covered. E1 (2026-08-20) is within the limit and not self-selected but covers G1 only; no evidence for G2.
Q2: partly covered. E2 (2026-09-30) is within the limit but self-selected and covers G1 only. E3 (2025-01-14) is older than the cutoff of 2025-11-10 and counts as old.
Q3: none. No evidence supplied.
Open questions: Q1, Q2, Q3

METHOD OPTIONS
Q1 (A):
M6 Records review. Covers: G1 (G2 holds no records). Fixed 16 h (3.0 days).
M5 Survey. Covers: G1, G2. Fixed 24 h (4.0 days). 30 responses per group; at a 15% response rate (default), 200 invitations per group.
M2 Observation in context. Covers: G1, G2. 8 participants at 5 h = 40 h (7.0 days).
Q2 (B):
M1 Interviews. Covers: G1, G2. 10 participants at 3 h = 30 h (5.0 days).
M2 Observation in context. Covers: G1, G2. 8 participants at 5 h = 40 h (7.0 days).
Q3 (C):
M3 Usability sessions. Covers: G1, G2. 10 participants at 3 h = 30 h (5.0 days).

PROPOSED SET
M1 for Q2; M3 for Q3; M6 for Q1. Participants: M1 5 per group in G1 and G2 (10); M3 5 per group in G1 and G2 (10); M6 none. Total 76 h (13.0 days) against 42 h (7.0 days) available: over by 34 h.
Without M1: 46 h (8.0 days), over by 4 h, leaves Q2 uncovered.
Without M3: 46 h (8.0 days), over by 4 h, leaves Q3 uncovered.
Without M6: 60 h (10.0 days), over by 18 h, leaves Q1 uncovered.
Hours per participant: M1 3 h; M3 3 h; M6 fixed hours in all, no figure per participant.
Wider cover: Q1: M6 covers G1 only; M5 covers G1 and G2 for 8 h more.

PARTICIPANTS
G1 Active subscribers who plan for several people. About 4,200. Reached by: email list of active subscribers. Needed: M1 5; M3 5; M6 records, no participants.
G1-U1 Opens the plan on a phone at least weekly. Ask: "In how many of the last four weeks did you open your meal plan on a phone?" (None / 1 / 2 / 3 / All four). Qualifies: All four.
G1-U2 Plans dinners for 3 or more people. Ask: "Including yourself, how many people do you usually plan dinners for?" (1 / 2 / 3 / 4 / 5 or more). Qualifies: 3, 4, 5 or more.
G1-X1 Works or has worked for the organization or its design suppliers (default). Research lead to check against the staff list.
G1-X2 Took part in one of the organization's studies in the last 6 months (default). Research lead to check against the participant log.
G2 Former subscribers. About 310. Reached by: email list of subscribers who cancelled in the last 90 days. Needed: M1 5; M3 5.
G2-U1 Cancelled in the last 90 days. Defines the list.
G2-X1 Works or has worked for the organization or its design suppliers (default). Research lead to check against the staff list.
G2-X2 Took part in one of the organization's studies in the last 6 months (default). Research lead to check against the participant log.
Criteria to add: none supplied
Not reachable: None

PERMISSIONS NEEDED
PM1 Use of the customer list to invite people. Needed by M1, M3. G1: granted (Head of Customer Care, 2026-10-30; email invitations to active subscribers). G2: not granted (Head of Customer Care; asked, no answer yet).
PM2 Consent to take part. Needed by M1, M3. All groups: granted (Research lead, 2026-10-28; consent text for sessions exists).
PM3 Consent to record. Needed by M1, M3, only if sessions are recorded (recording undecided). All groups: not stated.
PM4 Access to usage records. Needed by M6. G1: granted (Data owner, 2026-10-28; product analytics events for active subscribers). Unclear: the note does not say whether the grant covers the records period, which is not stated.
PM5 Handling of notes and data. Needed by M1, M3, M6. All groups: not stated.
PM6 Incentive approved. Needed by M1, M3, only if an incentive is offered (incentive undecided). All groups: not granted (Head of Product; no incentive budget approved).
PM7 Access to the design being shown. Needed by M3. All groups: granted (Product owner, 2026-11-06; prototype build of the plan screen). Unclear: the note does not say whether the prototype shows both the list view and the grid view that Q3 asks about.
Other permissions supplied: None

ANALYSIS APPROACH
M1 Interviews: notes by participant id (R01, R02); each statement coded to the question it speaks to (Q2); a pattern reported for a group only when more than half its participants raised it; anything less reported as a single account with its participant id; quotations cited to the participant id.
M3 Usability sessions: each participant's attempt at each task recorded as completed without help, completed after a prompt or not completed (Q3); reported as counts out of the group, not percentages while a group has fewer than 20 participants.
M6 Records review: before any data is pulled, the research lead writes the measure for Q1, the group (G1) and the records period; records period not stated; results show what happened and how often, never why.
Rules for reading the evidence: fixed before fieldwork; any change after data arrives is logged with its reason
Result that would change the decision: ______, written by the research lead before fieldwork

WHAT THE STUDY CANNOT ESTABLISH
1. M1 Interviews: what the few people say, not how many people hold a view; accounts of past behaviour can differ from what people did.
2. M3 Usability sessions: whether these people could finish these tasks with this design, not whether they would choose it, keep using it or pay for it.
3. M6 Records review: what happened in the records for the groups they cover and the period reviewed, not why it happened.
4. Q1 for G2: M6 covers G1 only, because no records are held for G2.
5. Sample basis: G1 and G2 are reached from lists the organization holds; only people on those lists can be reached.
6. Existing evidence: E2 comes only from people who wrote in, and E3 is older than the 12-month limit; neither is relied on for Q2.
7. Size: M1 and M3 use 5 participants per group; results are counts among those five, not shares of the group.
Questions left uncovered by the proposed set: None

DECISIONS FOR THE RESEARCH LEAD: 6
1. Time. The proposed set takes 76 h (13.0 days) against 42 h (7.0 days): over by 34 h. Which method to leave out, or how many participants to cut? Leaving out M1 leaves Q2 uncovered, M3 leaves Q3, M6 leaves Q1; each participant fewer in M1 or M3 saves 3 h.
2. Method and types. Confirm the types of Q1 (A), Q2 (B) and Q3 (C) and the method for each. For Q1, M6 covers G1 only; M5 would cover G1 and G2 for 8 h more.
3. Participants. Approve G1-U1, G1-U2 and G2-U1, the answers that qualify (G1-U1 reads "at least weekly" and the question qualifies only "All four" of the last four weeks), the standing exclusions and 5 participants per group for M1 and M3. No criteria beyond the group definition were supplied for G2.
4. Permissions. PM1 for G2 is not granted (Head of Customer Care; asked, no answer yet). PM5 is not stated: where notes are kept, who sees them and for how long, and who decides, are not given. PM4 is granted for G1 but the note does not say whether it covers the records period, which is not stated (Data owner). PM7 is granted but the note does not say whether the prototype shows both views (Product owner).
5. Recording and incentive. Whether to record sessions and whether to offer an incentive. If recording, PM3 is not stated. If an incentive, PM6 is not granted (Head of Product; no incentive budget approved).
6. Result that would change the decision. Write, before fieldwork, the result that would change the decision on the default view of the plan screen on phones.

Draft for the Research lead's approval. Nobody has been contacted or recruited, nothing has been sent or changed, and no finding is stated.
```

Every figure traces to the inputs above: the evidence dates and the cutoff of 2025-11-10, the default hours and participants per group in the template, and the permission lines supplied. The exception is the screening questions, where the assistant proposed the period ("the last four weeks") and the words "meal plan", which the inputs do not give; the research lead confirms them.
