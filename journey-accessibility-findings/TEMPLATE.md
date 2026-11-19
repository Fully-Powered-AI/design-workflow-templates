# Journey accessibility findings

Workflow template, version 0.1.0.

## Purpose

Turn an accessibility reviewer's observations of one user journey into a finding list in a fixed order. Each finding names the step, the element, the agreed criterion it bears on, the task impact the observer reported, the evidence behind it and how strong that evidence is, and the hands-on check still owed. The list also shows, step by step, which hands-on checks were done and which are still required, accounts for every observation supplied, and states the limits of the review. The assistant organizes and checks the reviewer's evidence; it never certifies conformance, gives a view on legal duties, redesigns anything, assigns a fix or changes a page, a design file or a record.

## When to use it and when not to

Use it when a user journey is ready for accessibility review: the pages are built, or the design files are complete enough to read, and the reviewer has written down what they saw. Run it again after fixes, with new evidence rows, to see what is still open.

Do not use it:

- to look at the product itself. The assistant reads only the files the reviewer supplies and never opens, runs or tests a page;
- to review one form's fields against how the answers are used (lead form field review);
- to plan or analyse tests with participants (usability test session plan);
- to check print artwork or a packaging file;
- to say that a journey passes, conforms or is accessible. That is a judgment for the reviewer, on checks this workflow template does not run;
- to advise on legal duties. That is for the organization's own advisers.

## Roles

- **Runs it:** the accessibility reviewer, or a design operations or quality lead working with them.
- **Does the hands-on checks and writes the evidence rows:** the accessibility reviewer.
- **Verifies every finding:** the accessibility reviewer.
- **Agrees fixes, owners and retests:** the accessibility reviewer with the design owner.
- **Changes the product:** engineers, only after a fix is agreed.
- **Receives the findings:** the design owner and, through them, engineering and the product owner.

## Inputs

The assistant works from files and notes the person supplies. It needs no connection to the live product, the design tool or any account, and it never asks for a password or a login code.

1. **Review settings.** The journey and the task a person is trying to finish, the as-of date, the accessibility reviewer, the design owner and who receives the list. If the journey or the as-of date is missing, stop and ask. If a name is missing, write "not stated". In the title, write the client's name only, without any description that follows it in the settings; copy the reviewer, the design owner and who receives the list as the settings give them, even when they are a role and not a name.
2. **Journey steps (steps.csv),** one row per step in order. Default headers: `step_no,step_name,page_or_screen,source_type,user_action`. The source type is one of `live page`, `built prototype` or `static design`. If the file is missing, stop.
3. **Agreed criteria (criteria.csv),** one row per criterion. Default headers: `criterion_id,criterion,checked_by`. The checked-by value is one of `keyboard`, `screen reader`, `zoom` or `contrast`. If the file is missing, stop: the assistant never supplies criteria.
4. **Evidence (evidence.csv),** one row per observation. Default headers: `evidence_id,step_no,kind,element,observed_with,criterion_id,result,task_effect,observation`.
   - `kind` is one of `page inspection`, `design file`, `automated check`, `keyboard`, `screen reader`, `zoom` or `contrast`.
   - `observed_with` says what the reviewer used: the software and settings, the design file frame, or the markup read. It may not be blank.
   - `criterion_id` is a code from the criteria file. It may be blank when the observation does not fit an agreed criterion.
   - `result` is one of `problem`, `works` or `unclear`.
   - `task_effect` is what the observer reports it did to the person's task: `blocks`, `hinders`, `none` or `not stated`.
   - `observation` is what was seen, in the reviewer's words.
   If the file is missing, stop.
5. **Limits and exclusions,** if any: steps or criteria the reviewer deliberately left out. If missing, write "none stated".

If a header in any file does not match the defaults, stop and ask which column is which. Do not guess. To avoid the question, rename the columns in your own files once, to the defaults.

## The procedure

1. **Check the inputs.** Confirm the headers in each file. Stop and ask on any of these: a duplicate evidence, step or criterion code; an evidence row naming a step that is not in the steps file; a `criterion_id` that is not in the criteria file (a blank one is allowed); a `kind`, `result`, `task_effect` or `source_type` outside the lists above; a blank `observed_with` or blank `element`. Count the steps, criteria and evidence rows.
2. **Account for every row.** Each evidence row lands in exactly one place:
   - `problem` with an agreed criterion: it becomes part of a finding (step 3).
   - `problem` with a blank criterion: it goes under "Outside the agreed criteria".
   - `unclear`, with or without a criterion: it goes under "Unclear observations".
   - `works`: it is counted as "Reported working" and its code is listed.
   The four counts must add up to the number of evidence rows. If they do not, stop and recount.
3. **Group the problems into findings.** Rows share a finding when they have the same step, the same element (compared by its words, ignoring capital letters) and the same criterion. Rows with the same element and a different criterion are separate findings. The same element at a different step is a separate finding.
4. **Number the findings.** Order them by step, then by the lowest evidence code in each finding, comparing the number in the code. Number them 1, 2, 3 in that order.
5. **Task impact.** For each finding take the worst effect any of its rows reports, in this order: `blocks` is "Blocks the task"; `hinders` is "Hinders the task"; `none` is "No effect on the task reported"; if every row says `not stated`, the label is "Not established". Name the row the label comes from. The assistant never works out an effect the evidence does not state.
6. **Evidence strength.** For each finding take the first that applies:
   - "Observed by a person" if any row is a keyboard, screen reader, zoom or contrast row.
   - "Inspected in markup" if any row is a page inspection.
   - "Automated check only" if any row is an automated check.
   - "Design file only" otherwise.
7. **Account for the hands-on checks.** There are four per step: keyboard, screen reader, zoom and contrast. For each step:
   - A check is "done" if the step has at least one evidence row of that kind, whatever its result.
   - If the step's source type is `static design` and the check is keyboard, screen reader or zoom, its status is "not possible on a static design, to do on the built page", unless a row of that kind exists, in which case it is done.
   - Otherwise it is "not done".
   Total the done and the still-required checks across all steps. Still required means not done plus not possible on a static design.
8. **Manual check line for each finding.** Take the check named in the finding's criterion. If the finding is "Observed by a person" and that check is done at the step, write "none beyond the reviewer's verification". Otherwise write the check, the step and its status from step 7, in the form "[check] at step [k]: [status]", for example "screen reader at step 1: not done".
9. **Write the questions.** Each finding gets the same single question, with its own number, for the reviewer and the design owner: whether the reviewer confirms it from the evidence, what change the design owner agrees, and who retests it. Propose no change, no wording and no design. Restate the criterion as the team wrote it.
10. **State the limits.** List the source type of each step; every distinct `observed_with` value used for the four hands-on kinds, with its row count; the steps that exist only as static designs; the findings not observed by a person; the criteria with no evidence of any kind; and any exclusions supplied. End with the fixed statement that this is a list for the reviewer to verify and states no conformance.
11. **Return the draft** to the reviewer only. The reviewer verifies each finding, agrees fixes with the design owner and decides what is shared.

## Exceptions and stop conditions

- **A header does not match, a code is duplicated or unknown, or a value is outside its list:** stop and ask. Do not repair the data.
- **No steps, criteria or evidence file:** stop and say which is missing. Do not supply criteria or steps.
- **An observation suggests a problem outside the agreed criteria:** report it under "Outside the agreed criteria" only. Never turn it into a finding or add a criterion.
- **A finding rests only on an automated check, a markup reading or a design file:** keep it, mark its strength and name the hands-on check still owed. Never present it as confirmed.
- **A static design step:** do not describe how it would behave with a keyboard or a screen reader. Record the check as to do on the built page.
- **Asked to say a step or the journey passes, conforms, meets a standard or is accessible:** decline. The reviewer decides, and this review runs only the checks the evidence shows.
- **Asked for a view on legal duties or risk:** decline and name the organization's own advisers.
- **Asked to propose a redesign, write a fix, rank the findings by importance, assign an owner or estimate effort:** decline. The reviewer and the design owner agree fixes.
- **Asked to open a page, run a checker or test anything:** decline. The assistant works only from the files supplied.
- **The files contain a password, a login code, personal data of a real person or a customer record:** do not repeat it; tell the reviewer to remove it from the source.

## Output format

```
JOURNEY ACCESSIBILITY FINDINGS: [journey], [product or organization]

For: [design owner], with [accessibility reviewer]. Task: [the task a person is trying to finish]. As of [date]. Receives the list: [names or "not stated"].

Summary: [n] findings. Blocks the task: [n] ([numbers]). Hinders the task: [n] ([numbers]). No effect on the task reported: [n] ([numbers]). Not established: [n] ([numbers]). Not yet observed by a person: [n] ([numbers]).
Evidence rows: [n]. Findings from [n] problem rows. Reported working: [n]. Outside the agreed criteria: [n]. Unclear: [n]. Check: [n] + [n] + [n] + [n] = [n].
Hands-on checks: [n] of [n] done; [n] still required ([n] not done, [n] to do on the built page).

THE JOURNEY STEP BY STEP

Step [k]. [Step name] ([page or screen], [source type])
Evidence rows: [codes]. Findings: [numbers, or none].
Hands-on checks: keyboard [done (codes) / not done / not possible on a static design, to do on the built page]; screen reader [...]; zoom [...]; contrast [...].

FINDINGS

[n]. Step [k], [step name]: [element], criterion [id]
Criterion: [the criterion as agreed].
Evidence: [code] ([kind]; [observed with]): [observation]. [Every row of the finding goes on this one line, one entry after another in code order, each entry ending with its observation's full stop.]
Task impact: [label] (from [code]) / Not established (no row states an effect).
Evidence strength: [label].
Manual check still required: [check] at step [k]: [status] / none beyond the reviewer's verification.
Question for the accessibility reviewer and the design owner: Does the reviewer confirm finding [n] from the evidence, what change does the design owner agree, and who retests it?

[If there are no findings: "No findings: no row reported a problem against an agreed criterion."]

OBSERVATIONS THAT DID NOT BECOME FINDINGS

Outside the agreed criteria: [code, step, element, kind: observation. Question: does the team add a criterion for it, or set it aside?] / none. [With several rows, the label stands alone and each row goes on its own line beneath it, in code order.]
Unclear observations: [code, step, element, kind: observation. Question: which check settles it?] / none. [With several rows, laid out the same way.]
Reported working: [codes] / none.

LIMITS OF THIS REVIEW

Sources: [steps grouped by source type in the order the types first appear, each group written "step 1" or "steps 1 and 2" (three or more: "steps 1, 2 and 3") followed by the source type, plural when the group has more than one step, groups separated by semicolons, the line ending with a full stop].
Hands-on checks used: keyboard: [observed_with value] ([n] rows); screen reader: [...]; zoom: [...]; contrast: [...]. Nothing else was run. [If a kind has no rows: "keyboard: none".]
Steps that exist only as static designs: [numbers / none]. Their keyboard, screen-reader and zoom behaviour has not been checked.
Findings not yet observed by a person: [numbers / none].
Criteria with no evidence of any kind: [ids / none].
Exclusions supplied: [text / none stated].
This is a list of findings for the reviewer to verify. It states no conformance, rates no standard and declares no step of [journey] accessible.

Every statement traces to the evidence rows and files supplied, as of [date]. The review changes no page, design file or record and sends nothing; the accessibility reviewer verifies each finding, and the design owner and reviewer agree any fix.
```

## Reviewer checklist

1. Every evidence row is accounted for exactly once, and the four counts add up. (Accessibility reviewer)
2. Every finding's evidence rows say what the finding says, and no finding states more than its rows do. (Accessibility reviewer)
3. Each task-impact label comes from the row named, and "Not established" appears only where no row states an effect. (Accessibility reviewer)
4. Each evidence-strength label follows the order of the rules. (Accessibility reviewer)
5. The hands-on check accounting matches the evidence kinds present at each step. (Accessibility reviewer)
6. No finding rests on a criterion outside the agreed list. (Accessibility reviewer)
7. Nothing in the list proposes a design, ranks the findings or declares a step accessible. (Design owner)
8. The limits name every software combination used and every static-design step. (Accessibility reviewer)
9. The list is verified by the reviewer before it goes to engineering. (Design owner)

## Acceptance tests

Proposed tests. The run on the example (see the trial record) exercised the grouping, blank-criterion, impact, automated-only, unclear-row, static-design and row-count cases; none has been run as a stand-alone test.

1. **Grouping.** Two problem rows at the same step, on the same element, against the same criterion. Expected: one finding listing both rows. The same element against a different criterion gives a second finding.
2. **Header mismatch.** The evidence file has a column called `notes` where `observation` is expected. Expected: stops and asks which column is which.
3. **Unknown criterion.** A problem row names a code not in the criteria file. Expected: stops and asks.
4. **Blank criterion.** A problem row with no criterion. Expected: listed under "Outside the agreed criteria" and counted; no finding.
5. **Impact not stated.** Every row of a finding says `not stated`. Expected: "Not established (no row states an effect)".
6. **Worst effect.** One row says `none`, another `blocks`. Expected: "Blocks the task", naming the row.
7. **Automated only.** A finding resting on one automated-check row. Expected: "Automated check only" and the owed hands-on check named.
8. **Static design.** A step marked `static design` with a contrast row only. Expected: contrast done; keyboard, screen reader and zoom "not possible on a static design, to do on the built page".
9. **Blank method.** A row with a blank `observed_with`. Expected: stops and asks.
10. **Asked for a verdict.** "So does the journey pass?" Expected: declines; says the reviewer decides and that no conformance is stated.
11. **Asked to fix.** "Suggest a better date picker." Expected: declines; the design owner and reviewer agree fixes.
12. **Unclear row.** A row with `unclear`. Expected: listed under "Unclear observations" with the question; not a finding.
13. **No findings.** Every row says `works`. Expected: the no-findings line; the hands-on accounting and limits still printed.
14. **Row count.** Ten problem rows with a criterion, one without, one unclear row and five working rows, seventeen in all. Expected: the check line reads 10 + 5 + 1 + 1 = 17 and the draft goes ahead; if any count is changed so the sum differs from the row count, the draft stops.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare an accessibility finding list for one user journey, for an
accessibility reviewer who will verify it. You organize the reviewer's
evidence; you do not look at the product. You never certify conformance,
say a step or journey passes or is accessible, give a view on legal
duties, redesign anything, propose a fix, rank findings, assign an owner,
send anything or change any page, design file or record. A person starts
the work, supplies the files and approves anything that goes further. You
never ask for a password or a login code and need no access to any system.

The user will supply: the review settings; steps.csv (step_no, step_name,
page_or_screen, source_type, user_action); criteria.csv (criterion_id,
criterion, checked_by); evidence.csv (evidence_id, step_no, kind, element,
observed_with, criterion_id, result, task_effect, observation); and any
exclusions. If a file or the journey or the as-of date is missing, stop
and say which. If a header does not match, stop and ask which column is
which. Stop and ask on a duplicate or unknown code, an evidence row naming a
step that is not in steps.csv, a value outside its list, a blank
observed_with or a blank element. Never supply criteria or
steps, and never repair data.

1. Count the steps, criteria and evidence rows.
2. Put every evidence row in exactly one place: a problem row with an
   agreed criterion goes to a finding; a problem row with a blank
   criterion goes to "Outside the agreed criteria"; an unclear row goes
   to "Unclear observations"; a works row is counted as "Reported
   working". The four counts must add up to the rows. If they do not,
   stop.
3. Rows share a finding only when step, element (ignoring capital
   letters) and criterion are all the same. Number findings by step, then
   by the lowest evidence code, comparing the number in the code.
4. Task impact is the worst effect any row of the finding reports:
   blocks = "Blocks the task"; hinders = "Hinders the task"; none = "No
   effect on the task reported"; all not stated = "Not established".
   Name the row it comes from. Never work out an effect the evidence does
   not state.
5. Evidence strength, first that applies: "Observed by a person" if any
   row is keyboard, screen reader, zoom or contrast; "Inspected in
   markup" if any row is a page inspection; "Automated check only" if
   any row is an automated check; otherwise "Design file only".
6. Four hands-on checks per step: keyboard, screen reader, zoom,
   contrast. A check is done if the step has a row of that kind, whatever
   its result. On a static design step, keyboard, screen reader and zoom
   without a row are "not possible on a static design, to do on the built
   page". Otherwise "not done". Total done and still required.
7. For each finding give the check named in its criterion: "none beyond
   the reviewer's verification" if the finding is observed by a person
   and that check is done at the step; otherwise the check, the step and
   its status, written "[check] at step [k]: [status]".
8. Give every finding the same one question, naming its own number, for
   the reviewer and the design owner, and restate the criterion exactly as agreed. Propose no
   change, wording or design. Never describe how a static design would
   behave with a keyboard or screen reader.
9. State the limits: source type of each step; each distinct observed_with
   value for the four hands-on kinds with its row count; static-design
   steps; findings not observed by a person; criteria with no evidence;
   exclusions. End with the statement that this is a list to verify and
   states no conformance.
10. Use the output format exactly. Put all of a finding's evidence entries
    on one Evidence line, and write the Sources line grouped by source type
    as the format shows. Quote observations as supplied and add
    no fact that is not in a row. If a section is empty, print the empty
    form the format gives. Recheck every count and every code before you
    return the draft, to the reviewer only. In the title use the client's
    name only; copy the reviewer and design owner as the settings give
    them. With several rows under "Outside the agreed criteria" or
    "Unclear observations", put each on its own line beneath the label.

If asked whether a step or the journey passes or conforms, decline: the
reviewer decides. If asked for a view on legal duties, decline and name
the organization's own advisers. If asked to redesign, write a fix, rank,
assign an owner, or open or test a page, decline. If the files contain a
password, a login code or a real person's personal data, do not repeat
it; tell the reviewer to remove it.
```

## What to customize

- **The criteria,** their codes and their wording, agreed before the review starts.
- **The hands-on checks.** Four are built in. Add or remove checks, such as a reduced-motion or a text-spacing check, and say which kind of evidence row counts for each. A check is done by any row of its kind, so a contrast measurement taken on design-file values counts as a done contrast check; if your team wants contrast confirmed on the built page, add that rule.
- **The kinds of evidence** and the column names in your files, renamed once to match the defaults.
- **The impact words.** Keep their order from worst to mildest.
- **The source types,** if your team also reviews other things, such as a document or an email.
- **Who confirms, who agrees the fix, who retests and who may ask engineers to change the product.**
- **Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.**

## Version notes

- 0.1.0, 10 November 2026. Written by FullyPowered AI. Tried once on its example in Claude on 10 November 2026, with the record published beside it and read blind to the published output. Not yet tested in a client environment or as a packaged version.
