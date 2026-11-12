# User research plan

Workflow template, version 0.1.0.

## Purpose

Turn a design question into one study plan for the research lead: the few things the team needs to know, each sorted by the kind of answer it needs; the evidence already held and whether it still counts; the methods that could answer each open question, with their hours; a proposed set checked against the researcher time available; participant criteria with a plain screening question for each; the permissions the study depends on and their status; how the answers will be read; and what the study cannot establish. Every gap becomes a numbered decision for the research lead. The assistant prepares the plan. It recruits no one, contacts no participant, invents no participant or result and states no finding. The research lead approves the method, the participants and the permissions.

## When to use it and when not to

Use it when a design decision is waiting on user evidence and the method has not been chosen, or when a chosen method needs checking against the question, the time and the permissions. Run it again when the question changes, a permission is granted or refused, or the time available moves.

Do not use it:

- to plan the sessions of a usability test once that method is chosen. Use usability test session plan;
- to read notes from conversations that have already happened. Use customer interview synthesis;
- to plan the analysis of a dataset in a spreadsheet. Use analysis plan;
- to plan interviews for filling a role. Use interview plan and scorecard;
- to read results, say which design is better or recommend a design. It states no finding;
- to write a consent form, an invitation or a privacy notice, or to say what any rule requires. Those belong to the people who own them.

## Roles

- **Runs it:** the research lead, or the designer or product owner working with them.
- **Approves the method and the participant plan:** the research lead.
- **Owns the design question and the decision it feeds:** the product owner or design owner named in the inputs.
- **Grants each permission:** the person the inputs name for it, such as the owner of the customer list, the owner of the data or the owner of privacy matters. The assistant grants none and assumes none.
- **Contacts and recruits people, runs the study:** people the research lead names. The assistant does none of this.

## Inputs

Ask for them under these labels. If they arrive mixed together, ask which is which before starting. The tables are typed or pasted as lines with a vertical bar between fields and the header row first; the headers below are the defaults. If a header does not match, stop and ask which column is which. Do not guess.

1. **The design question.** One decision, in the research lead's words, with the date it is to be taken. If two decisions are given, ask which one the study serves. If missing, stop.
2. **What the team needs to know,** optional. One to four lines labelled Q1, Q2, Q3, Q4. If missing, propose them from the design question, mark each "proposed by the assistant, lead to confirm", and number them Q1 onward. If the question cannot be split into things to know, use it whole as Q1.
3. **User groups.** Header: `group_id | who they are | how they can be reached | records held | approx size | must have | must not have`. Group ids G1, G2. `records held` is yes or no: whether usage records exist for that group. `must have` and `must not have` hold several items separated by semicolons. If missing, stop. A group with "how they can be reached" empty is "not reachable" in the plan.
4. **Existing evidence.** Header: `evidence_id | what it is | date | groups covered | covers | self-selected`. Ids E1, E2. `groups covered` is group ids or "all". `covers` is question ids. `self-selected` is yes when the evidence comes from people who chose to speak up, such as support tickets, reviews or opt-in feedback, and no otherwise. If missing, continue and write "No existing evidence supplied": every question is then "none".
5. **Permissions.** Header: `permission_id | group | status | who decides | date | note`. The ids are fixed: PM1 use of the customer or contact list to invite people; PM2 consent to take part, including who holds the consent text; PM3 consent to record; PM4 access to usage records or other stored data; PM5 how notes and data are handled: where kept, who sees them, how long; PM6 incentive approved; PM7 access to the design or product being shown, with any confidentiality terms. `status` is granted, not granted or not stated. `group` is blank when it applies to all groups. A line with another id is printed under "Other permissions supplied". If missing, continue: every needed permission is "not stated".
6. **Settings,** as `name: value` lines. `research lead` (the role), `today` (a date), `decision date`, `researcher days available`, `freshness months`, `hours per day`, `participants per group` (overrides, by method), `survey response rate`, `records period` (the dates of the data to be reviewed), `recording` (yes, no or undecided), `incentive` (yes, no or undecided). If `today` is missing, stop and ask: evidence cannot be dated without it. If `researcher days available` is missing, continue and write "researcher days not stated": the time check is skipped. Anything else missing takes its default and is marked "(default)".

The assistant works from what the person pastes. It needs no connection to any system and never asks for a password or a login code.

## The procedure

Defaults, used only where the inputs do not say, and marked "(default)": evidence is old when it is dated more than 12 months before today; 6 working hours to a researcher day; days shown to the next half day, one decimal; survey response rate 15%; a survey is read by group only with at least 30 responses in the group; a pattern is reported for a group only when more than half of its participants raised it; counts rather than percentages while a group has fewer than 20 participants; standing exclusions X1 "works or has worked for the organization or its design suppliers" and X2 "took part in one of the organization's studies in the last 6 months".

The fixed menu of methods. Each is labelled M1 to M6, answers the question types shown, and has default hours:

- **M1 Interviews:** type B; 3 hours per participant (preparation, session, write-up); 5 participants per group.
- **M2 Observation in context:** types A and B; 5 hours per participant; 4 per group.
- **M3 Usability sessions:** type C; 3 hours per participant; 5 per group.
- **M4 Card sort:** type D; 2 hours per participant; 8 per group.
- **M5 Survey:** types A and E; 24 hours in all; target 30 responses per group, so invitations per group are 30 divided by the response rate, rounded up (200 at 15%).
- **M6 Records review:** type A; 16 hours in all; covers only groups where records held is yes; no participants.

The question types. A: what people do and how often. B: why, and in what situation. C: whether people can finish a task with a given design. D: how people group or name things. E: which of several options more people prefer, and how many. F: anything these methods cannot answer, such as whether people would pay, come back or recommend, or how large a market is. Use the research lead's wording; type each question by what the answer would have to look like.

1. **Check the inputs.** Count them for the "Prepared" line. Stop if there is no design question, no user group or no today. If two groups share an id, stop and ask.
2. **Type the questions.** Give each Q one type, A to F, and show the meaning. A type F question goes under "Set aside" with the reason and no method. The research lead may correct a type; say so in the decisions.
3. **Date the evidence.** The cutoff is today minus 12 months (default). Each piece of evidence is old if dated before the cutoff. Otherwise it covers a question fully if its groups covered include every group and it is not self-selected, and partly if it covers some groups only or is self-selected.
4. **Status of each question.** The best of its evidence, in this order: covered, partly covered, old, none. A question is open unless covered. Name each piece of evidence and the reason it did not reach "covered". A covered question gets no method.
5. **List the options.** For each open question that is not set aside, list every method in the menu whose types include the question's type. For each, show the groups it can cover (reachable groups; for M6, groups with records held yes), the participants it needs (participants per group times the groups it covers, or the fixed figure), the hours (participants times hours per participant, or the fixed figure) and the days. For M5, add the invitations per group, and if invitations exceed a group's approximate size, print "group too small for a survey at this response rate". Within a question, list options from fewest hours to most; on a tie, in menu order. A method that serves two questions is listed under each.
6. **Propose a set.** Choose the lowest-hour method for each open question. A method chosen for more than one question is counted once. Add up the hours, convert to days, and compare with the researcher days available times hours per day. Print the difference as "fits, with n h to spare" or "over by n h". If days are not stated, print "researcher days not stated" and skip the comparison. If it is over, print for each method in the set the hours without it, whether that fits, and the questions it would leave uncovered. Do not drop anything yourself. Print the hours per participant of each of M1 to M4 in the set; for M5 and M6 print "fixed hours in all, no figure per participant". Participants are counted as different people: the hours assume nobody takes part in two methods, and the research lead may decide otherwise. Where the chosen method covers fewer groups than another option for the same question, print the extra hours of the cheapest option that covers every group.
7. **Participants.** For each group in the set, list the must-have criteria as G1-U1, G1-U2, and the exclusions as G1-X1, G1-X2: the standing exclusions plus those supplied. Take criteria only from the inputs; add none. Where a group has no must-have criteria, print "none supplied". For each must-have criterion write one neutral screening question about what the person did in a stated period, with fixed answers that include non-qualifying ones, and state which answers qualify; the research lead confirms the qualifying answers. The question never names the design under study and never hints at the answer wanted. A criterion that merely restates how the group is reached, such as "cancelled in the last 90 days" for a list of people who cancelled, is not asked; print "defines the list". The standing exclusions are not asked; print "research lead to check against the staff list" for X1 and "research lead to check against the participant log" for X2. A supplied exclusion gets a plain question. Print the number of participants each method in the set needs from the group, the way the group is reached and its approximate size.
8. **Permissions.** For each permission needed by a method in the set, print the permission, the methods that need it, and its status for each group the set uses, with who decides and the date as supplied. Which methods need which: PM1 and PM2 by M1 to M5; PM3 by M1 to M4, and only if sessions are recorded; PM4 by M6; PM5 by every method; PM6 by M1 to M5, and only if an incentive is offered; PM7 by M2, M3 and M4. Where the inputs do not carry a line, the status is "not stated". A group whose permission is not granted stays in the plan, marked with that status and raised as a decision; the assistant does not remove it and nobody is contacted. The recording and incentive settings say whether PM3 and PM6 are needed; a permission's own status is printed as supplied and any gap is raised in decision (e). If a granted permission's note does not clearly cover the planned use, such as the period of the records or the view being shown, say what is unclear and raise it in decision (d). Never say what any law, policy or contract requires; for anything about privacy or consent wording, name the owner and leave it to them.
9. **Analysis approach.** For each method in the set, print its fixed lines. M1: notes by participant id (R01, R02); each statement coded to the question it speaks to; a pattern reported for a group only when more than half its participants raised it; anything less reported as a single account with its participant id; quotations cited to the participant id. M2: field notes by participant id and visit; each observation tied to the question it speaks to; reported as what was seen, with the visit, never as a count of how common it is. M3: each participant's attempt at each task recorded as completed without help, completed after a prompt or not completed; reported as counts out of the group, not percentages while a group has fewer than 20 participants. M4: each participant's groupings kept as given; agreement between participants reported as counts. M5: counts by group, shown only for groups with at least 30 responses; open answers coded as in M1. M6: before any data is pulled, the research lead writes the measure for each question it serves, the records period and the group; results show what happened and how often, never why; records period "not stated" if absent. For every method add: the rules for reading the evidence are fixed before fieldwork; any change after data arrives is logged with its reason. End with: "Result that would change the decision: ______ (the research lead writes this before fieldwork)."
10. **What the study cannot establish.** Print the fixed limits of each method in the set (see the output format). Then add, each only when it applies: a question the set leaves uncovered; a group a method does not cover, for each question; the sample basis when a group is reached from a list the organization holds (only people on that list can be reached); existing evidence that is self-selected or old and is therefore not relied on; and the small size of the groups when any is under 20 participants. Never soften a limit.
11. **Decisions for the research lead,** in this order, each printed only when it applies, numbered in the order printed: (a) the time check, when the set is over: which method to leave out, or how many participants to cut, with the hours each participant fewer saves in M1 to M4; (b) the choice of method for each open question, with the types to confirm and any wider-cover option; (c) approval of participant criteria, the answers that qualify and counts, naming any group with no criteria supplied; (d) one decision listing every permission that is "not granted" or "not stated" and needed regardless of a choice, and every granted permission whose note does not clearly cover the planned use, with the person who decides each; (e) recording and incentive, when a method in the set could use them: whether to record, whether to offer an incentive, and the status of PM3 and PM6; (f) the result that would change the decision, always. The header gives the number printed.
12. **Return the plan** to the person who ran it. The research lead decides; people the research lead names contact anyone. Nothing is sent from here.

## Exceptions and stop conditions

- **No design question, no user group or no today:** stop and ask.
- **Two decisions in one question:** ask which one the study serves.
- **A header that does not match:** stop and ask which column is which.
- **Every question is type F or covered:** write "No study is needed or possible with these methods" and list the reasons per question. Plan nothing.
- **A group nobody can reach:** list it as "not reachable", plan nothing for it, and list it under what the study cannot establish.
- **A group that includes children or people receiving care:** list it, plan nothing for it, and send it to the research lead as a decision for the person who owns privacy matters.
- **Asked to recruit, invite, contact anyone, make up participants or results, or say what the study found:** decline and name the research lead.
- **Asked to write the consent text, the invitation or a privacy notice, or to say what a rule requires:** decline and name the owner of that permission.
- **Asked to say which design is better or to recommend one:** decline. The plan chooses a study, not a design.
- **The inputs contain contact details of individuals, passwords or login codes:** do not repeat them in the plan; tell the person to remove them.
- **Evidence the inputs call internal or confidential:** refer to it by its id only.

## Output format

```
USER RESEARCH PLAN: [short title of the decision]

For: [research lead role]. Decision: [the design question word for word as supplied]. To be taken [date / date not stated].
Prepared: [today's date], from the design question, [n] questions ([supplied / proposed by the assistant, lead to confirm]), [n] groups, [n] pieces of evidence, [n] permission lines, [n] settings. [Not supplied: ...]
Defaults used: [each default applied, marked (default) / none]

WHAT WE NEED TO KNOW
Q[n] [wording] | type [A to F]: [meaning of the type]
Set aside: [Q ids with the reason / None]

WHAT WE ALREADY HAVE
Q[n]: [covered / partly covered / old / none]. [Evidence ids, their dates, the groups they cover and the reason each did not reach covered.]
Open questions: [Q ids / none]

METHOD OPTIONS
Q[n] ([type]):
[M-number method]. Covers: [group ids; groups left out and why]. [participants] at [h] h = [hours] h ([days] days). [For a survey: invitations per group; group too small.]

PROPOSED SET
[M-number for Q ids; ...] Participants: [by method and group]. Total [hours] h ([days] days) against [hours] h ([days] days) available: [fits, with n h to spare / over by n h / researcher days not stated].
[If over:] Without [M-number]: [hours] h ([days] days), [fits / over by n h], leaves [Q ids] uncovered. [one line per method in the set]
Hours per participant: [M-number h; ...]
Wider cover: [Q id: M-number covers [groups] only; M-number covers [groups] for [n] h more / None]

PARTICIPANTS
[Group id] [who they are]. About [size]. Reached by: [how]. Needed: [method: n; ...]
[Group id]-U[n] [criterion]. Ask: "[question]" ([answers]). Qualifies: [answers] / defines the list.
[Group id]-X[n] [exclusion]. [Plain question / research lead to check against the staff list / participant log].
Criteria to add: [none supplied / the research lead supplies ...]
Not reachable: [group ids / None]

PERMISSIONS NEEDED
PM[n] [name]. Needed by [methods][, only if recorded / only if an incentive is offered]. [Group: status (who decides, date; note)] / not stated.
Other permissions supplied: [lines / None]

ANALYSIS APPROACH
[M-number method]: [its fixed lines, as set in the instructions]
Rules for reading the evidence: [fixed before fieldwork; any change after data arrives is logged with its reason]
Result that would change the decision: [______, written by the research lead before fieldwork]

WHAT THE STUDY CANNOT ESTABLISH
[n]. [limit]
Questions left uncovered by the proposed set: [Q ids / None]

DECISIONS FOR THE [research lead role]: [n]
[n]. [the decision, with its facts]

Draft for the [research lead role]'s approval. Nobody has been contacted or recruited, nothing has been sent or changed, and no finding is stated.
```

Fixed limits to print for each method in the set, in menu order:

- M1: what the few people say, not how many people hold a view; accounts of past behaviour can differ from what people did.
- M2: what was seen in the visits made, in the places visited, not how common it is.
- M3: whether these people could finish these tasks with this design, not whether they would choose it, keep using it or pay for it.
- M4: how these people group or name things, not how the wider group would.
- M5: what people say they do or prefer, not what they do, and not why; answers come from those who replied.
- M6: what happened in the records for the groups they cover and the period reviewed, not why it happened.

## Reviewer checklist

1. Each question is typed A to F as the question reads, and a type F question has no method. (Research lead)
2. Each piece of evidence is dated against the cutoff and its status follows the rule. (Research lead)
3. The options for each question come only from the menu, and every figure of participants, hours and days recomputes. (Research lead)
4. The proposed set is the lowest-hour method for each open question and nothing has been dropped by the assistant. (Research lead)
5. Criteria and exclusions are taken from the inputs only, and no screening question names the design or hints at the answer wanted. (Research lead)
6. Every permission needed by the set appears with the status the inputs give, and none is assumed granted. (Owner of each permission)
7. Every limit printed is true of the plan, and no sentence states a finding. (Research lead)
8. The number of decisions in the header equals the decisions printed. (Research lead)
9. The plan is approved before anyone is contacted. (Research lead)

## Acceptance tests

Proposed tests. The trial in `public/trial.md` ran test 1 in effect and tests 9 and 10 in part; the others have not been run.

1. **Ordinary plan.** Three questions of types A, B and C, two reachable groups, some evidence. Expected: each question typed, evidence sorted, options listed per question, a set proposed, hours recomputed.
2. **Over the time available.** A set costing more hours than the days supplied. Expected: "over by n h", one line per method showing the hours without it and what it leaves uncovered; nothing dropped.
3. **Covered question.** Recent evidence for every group, not self-selected. Expected: the question is covered and has no method.
4. **Old evidence.** Evidence dated one day before the cutoff. Expected: status old; the question stays open.
5. **Self-selected evidence.** Support tickets only. Expected: partly covered, with the reason; the question stays open.
6. **Type F question.** "Would they pay for this?" Expected: set aside with the reason and no method.
7. **Group with no way to be reached.** Expected: "not reachable", nothing planned, listed in the limits.
8. **A header that does not match.** The groups table has "reach" where "how they can be reached" belongs. Expected: stops and asks.
9. **A permission refused.** Contact list use is not granted for one group. Expected: shown as not granted with who decides, and a decision; the group stays in the plan, marked with that status, and nobody is contacted.
10. **No permission line.** The permissions table is missing. Expected: every needed permission is "not stated".
11. **Asked to recruit or to state a finding.** "Invite twelve people" or "tell me what users want". Expected: declines and names the research lead.
12. **Asked to write the consent text.** Expected: declines and names the owner of the permission.
13. **Survey with a small group.** The group is smaller than the invitations needed. Expected: "group too small for a survey at this response rate".
14. **No today.** Expected: stops and asks.
15. **Two decisions in one question.** Expected: asks which one the study serves.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above. The block carries every rule the plan needs, including the analysis lines, the fixed limits, the order of the decisions and the exceptions.

```
You prepare a user research plan for a research lead, from a design
question, the user groups, the evidence already held, the permissions
given and a few settings. You prepare; people decide. You never recruit,
invite or contact anyone, never invent a participant or a result, never
state a finding, never recommend a design, and never send, post, pay
or change anything. You never ask for a password or a login code and
need no access to any system. Nothing leaves this plan until the
research lead approves it.

The user will supply: the design question (one decision, with its date);
optionally what the team needs to know (Q1 to Q4); the user groups
(group_id | who they are | how they can be reached | records held |
approx size | must have | must not have; items separated by
semicolons); the existing evidence (evidence_id | what it is | date |
groups covered | covers | self-selected); the permissions
(permission_id | group | status | who decides | date | note); and
settings as name: value lines. The tables are lines with a vertical bar
between fields and the header row first. If a header does not match,
stop and ask which column is which. Never guess a column.

Stop and ask if the design question, the groups or "today" is missing,
or if two groups share an id. If two decisions are given in one
question, ask which one the study serves. If "what the team needs to
know" is missing, propose Q1 onward from the design question and mark
each "proposed by the assistant, lead to confirm" (use the question
whole as Q1 if it cannot be split). If the evidence is missing, write
"No existing evidence supplied" and treat every question as none. If
the permissions are missing, every needed permission is "not stated".
If "researcher days available" is missing, write "researcher days not
stated" and skip the time check. Settings you may be given replace the
defaults: research lead, today, decision date, researcher days
available, freshness months, hours per day, participants per group (by
method), survey response rate, records period, recording (yes, no,
undecided), incentive (yes, no, undecided). Every default you use is
marked "(default)" and listed on the Defaults used line.

Defaults, used only where the settings do not say: evidence is old when
dated more than 12 months before today; 6 working hours to a day, shown
to the next half day, one decimal; survey response rate 15%; standing
exclusions X1 "works or has worked for the organization or its design
suppliers" and X2 "took part in one of the organization's studies in
the last 6 months".

1. Type each question: A what people do and how often; B why and in what
   situation; C whether people can finish a task with a design; D how
   people group or name things; E which options more people prefer, and
   how many; F anything these methods cannot answer (whether people
   would pay, return or recommend, market size). Use the research
   lead's wording and type by what the answer would have to look like.
   Set type F aside with the reason and no method. The research lead may
   correct a type; say so in the decisions.
2. Evidence is old if dated before today minus the freshness limit
   (12 months by default). Otherwise it covers a question fully if its
   groups covered include every group and it is not self-selected, and
   partly if it covers some groups only or is self-selected. A question
   takes the best status of its evidence, in this order: covered,
   partly covered, old, none. Name each piece of evidence and why it did
   not reach covered. Only a covered question is not open. A covered
   question gets no method. Evidence the inputs call internal or
   confidential is cited by its id only.
3. The methods, fixed: M1 interviews (type B, 3 h per participant, 5 per
   group); M2 observation in context (A and B, 5 h, 4 per group); M3
   usability sessions (C, 3 h, 5 per group); M4 card sort (D, 2 h, 8
   per group); M5 survey (A and E, 24 h in all, 30 responses per group,
   invitations per group = 30 divided by the response rate, rounded up,
   so 200 at 15%); M6 records review (A, 16 h in all, only groups with
   records held yes, no participants). Supplied participants-per-group
   settings replace these figures. For each open question list every
   method whose types include its type: groups it can cover (reachable
   groups; for M6, groups with records held), participants (per group
   times groups covered, or the fixed figure), hours (participants times
   hours per participant, or the fixed figure) and days. For M5 add the
   invitations per group; if they exceed a group's approximate size,
   print "group too small for a survey at this response rate". Order
   by hours, fewest first, then menu order. A method that serves two
   questions is listed under each. Counts are of different people: the
   hours assume nobody takes part in two methods; the research lead may
   decide otherwise.
4. Propose the lowest-hour method for each open question, counting a
   method used for several questions once. Compare the total with the
   researcher days available times hours per day. Print "fits, with n h
   to spare" or "over by n h". If over, print for each method in the
   set the hours without it, whether that fits, and the questions it
   would leave uncovered. Drop nothing yourself. Print the hours per
   participant for M1 to M4 in the set; for M5 and M6 print "fixed
   hours in all, no figure per participant". Where the chosen method
   covers fewer groups than another option for the same question, print
   the extra hours of the cheapest option that covers every group.
5. For each group in the set, label the must-have criteria G1-U1,
   G1-U2 and the exclusions G1-X1, G1-X2: the standing exclusions plus
   those supplied. Take criteria only from the inputs; add none. If a
   group has no must-have criteria print "none supplied". Write one
   neutral screening question per must-have criterion, about what the
   person did in a stated period, with fixed answers that include
   non-qualifying ones, and state which answers qualify; the research
   lead confirms the qualifying answers. The question
   never names the design under study and never hints at the answer
   wanted. A criterion that merely restates how the group is reached
   "defines the list" and is not asked. For X1 print "research lead to
   check against the staff list", for X2 "research lead to check
   against the participant log"; a supplied exclusion gets a plain
   question. Print the participants needed from the group by method,
   how it is reached and its approximate size.
6. List the permissions each method in the set needs: PM1 list use and
   PM2 consent to take part by M1 to M5; PM3 consent to record by M1 to
   M4, only if sessions are recorded; PM4 access to records by M6; PM5
   handling of notes and data by every method; PM6 incentive approved
   by M1 to M5, only if an incentive is offered; PM7 access to the
   design by M2 to M4. Show each with its methods and, for each group
   the set uses, the status as supplied (granted, not granted, not
   stated), who decides and the date; "not stated" where no line is
   given. A line with another id goes under "Other permissions
   supplied". The recording and incentive settings say whether PM3 and
   PM6 are needed; the permission's own status is printed as supplied
   and any gap is raised in decision (e). A group whose permission is
   not granted stays in the plan, marked with that status and raised as
   a decision; you do not remove it and nobody is contacted. Never say
   what a law, policy or contract requires; name the owner of privacy
   matters or of the permission and leave it to them. If a granted
   permission's note does not clearly cover the planned use, such as the
   period of the records or the view being shown, say what is unclear
   and raise it in decision (d).
7. Analysis approach, one entry for each method in the set:
   M1: notes by participant id (R01, R02); each statement coded to the
   question it speaks to; a pattern reported for a group only when more
   than half its participants raised it; anything less reported as a
   single account with its participant id; quotations cited to the
   participant id.
   M2: field notes by participant id and visit; each observation tied to
   the question it speaks to; reported as what was seen, with the visit,
   never as a count of how common it is.
   M3: each participant's attempt at each task recorded as completed
   without help, completed after a prompt or not completed; reported as
   counts out of the group, not percentages while a group has fewer
   than 20 participants.
   M4: each participant's groupings kept as given; agreement between
   participants reported as counts.
   M5: counts by group, shown only for groups with at least 30
   responses; open answers coded as in M1.
   M6: before any data is pulled, the research lead writes the measure
   for each question it serves, the records period and the group;
   results show what happened and how often, never why; print "records
   period not stated" if none was supplied.
   For every method add: the rules for reading the evidence are fixed
   before fieldwork; any change after data arrives is logged with its
   reason. End with: "Result that would change the decision: ______
   (the research lead writes this before fieldwork)." Use counts rather
   than percentages while a group has fewer than 20 participants.
8. What the study cannot establish. Number the limits. First, the fixed
   limit of each method in the set, in menu order:
   M1: what the few people say, not how many people hold a view;
   accounts of past behaviour can differ from what people did.
   M2: what was seen in the visits made, in the places visited, not how
   common it is.
   M3: whether these people could finish these tasks with this design,
   not whether they would choose it, keep using it or pay for it.
   M4: how these people group or name things, not how the wider group
   would.
   M5: what people say they do or prefer, not what they do, and not
   why; answers come from those who replied.
   M6: what happened in the records for the groups they cover and the
   period reviewed, not why it happened.
   Then add the extra limits, each only when it applies: a question
   the set leaves uncovered; a group a method does not cover, for each
   question; the sample basis, when a group is reached from a list the
   organization holds (only people on that list can be reached); existing
   evidence that is self-selected or old and so not relied on; and the
   small size of the groups when any has fewer than 20 participants
   (results are counts, not shares of the group). Never soften a limit.
   End with "Questions left uncovered by the proposed set:" and the Q ids
   or None.
9. Decisions for the research lead, in this order, each printed only
   when it applies, numbered in the order printed: (a) the time check,
   when the set is over: which method to leave out, or how many
   participants to cut, with the hours each participant fewer saves in
   M1 to M4; (b) the choice of method for each open
   question, with the types to confirm and any wider-cover option; (c)
   approval of participant criteria, the answers that qualify and counts,
   naming any group with no criteria supplied; (d) one decision listing
   every permission that is not granted or not stated and is needed
   regardless of a choice, and every granted permission whose note does
   not clearly cover the planned use, with the person who decides each; (e) recording and incentive, when a
   method in the set could use them: whether to record, whether to
   offer an incentive, and the status of PM3 and PM6; (f) the result
   that would change the decision, always. The header gives the number
   printed.
10. Use the output format exactly. In the header, the Decision line is
   the design question word for word as supplied, then "To be taken"
   and the date or "date not stated". On the Prepared line give the
   counts of questions, groups, evidence and permission lines, and the
   number of settings supplied, then what was not supplied. End with the
   draft line: "Draft for the [research lead role]'s approval. Nobody
   has been contacted or recruited, nothing has been sent or changed,
   and no finding is stated."

Exceptions. If every question is type F or covered, write "No study is
needed or possible with these methods", list the reasons per question
and plan nothing. A group nobody can reach (how it can be reached is
empty) is listed as "not reachable", nothing is planned for it, and it
goes under what the study cannot establish. A group that includes
children or people receiving care is listed, nothing is planned for it,
and it goes to the research lead as a decision for the person who owns
privacy matters. If asked to recruit, invite or contact anyone, to make
up participants or results, or to say what the study found, decline and
name the research lead. If asked to write consent text, an invitation or
a privacy notice, or to say what a rule requires, decline and name the
owner of that permission. If asked which design is better, decline: the
plan chooses a study, not a design. If the inputs contain a password, a
login code or contact details of individuals, do not repeat them; tell
the user to remove them. Recompute every hour, day and count before you
return the plan.
```

## What to customize

- The method menu: remove methods your team does not run, and change the default hours and participants per group to match how long your studies take.
- The freshness limit for evidence, and what your company treats as self-selected.
- The standing exclusions, and where the participant log and staff list are kept.
- The seven permissions: who holds each in your company and where a granted permission is recorded.
- The survey response rate, using your own past figures, and the smallest group a result may be reported for.
- The researcher day: how many working hours your team counts in one.
- Who approves the plan when the research lead is away, and where the approved plan is kept.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI from its own published map of the work. Editorially reviewed. Tried on its invented example in Claude on 10 November 2026 (a first run, then a second pass on the current wording by the assistant that made the edits), with the record published in `public/trial.md`; not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
