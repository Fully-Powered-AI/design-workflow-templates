# User research plan: tried on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example in `public/example.md` (sections 1 to 6, the invented meal-planning app "Product Q"). No client data was used. The assistant that ran the template did not write it. It read the template and only the inputs of the example, produced the plan, and only then read the example's output to compare.

## Inputs used

The design question, the three questions Q1 to Q3, groups G1 and G2, evidence E1 to E3, the eight permission lines and the settings, exactly as listed under "The inputs" in `public/example.md`. The instruction block and output format were taken from `member/template.md`.

## What came out

All the required parts of the output format were produced, in order: title and header, what we need to know, what we already have, method options, proposed set, participants, permissions, analysis approach, what the study cannot establish, decisions (6) and the closing draft line. The substantial parts follow.

- **Questions:** Q1 type A, Q2 type B, Q3 type C. Nothing set aside.
- **Evidence (cutoff 2025-11-10):** Q1 partly covered (E1 covers G1 only). Q2 partly covered (E2 is self-selected and covers G1 only; E3, dated 2025-01-14, is old). Q3 none. All three questions stay open.
- **Options:** Q1: M6 16 h (3.0 days), M5 24 h (4.0 days, 200 invitations per group), M2 40 h (7.0 days). Q2: M1 30 h (5.0 days), M2 40 h (7.0 days). Q3: M3 30 h (5.0 days).
- **Proposed set:** M6 for Q1, M1 for Q2, M3 for Q3. Total 76 h (13.0 days) against 42 h (7.0 days) available: over by 34 h. Without M6: 60 h, over by 18 h, leaves Q1 uncovered. Without M1: 46 h, over by 4 h, leaves Q2 uncovered. Without M3: 46 h, over by 4 h, leaves Q3 uncovered. Wider cover for Q1: M5 covers G1 and G2 for 8 h more than M6. Nothing was dropped.
- **Participants:** M1 5 per group and M3 5 per group, in G1 and G2 (10 each); M6 uses G1 records and no participants. G1 screening questions: how many of the last four weeks the person opened the plan on a phone (qualifies: all four), and how many people they usually plan dinners for (qualifies: 3 or more). G2's only criterion, cancelled in the last 90 days, "defines the list" and is not asked. Standing exclusions X1 and X2 are left to the research lead to check against the staff list and the participant log.
- **Permissions:** PM1 granted for G1, not granted for G2 (no answer yet); PM2 granted for all; PM3 not stated (only if recorded); PM4 granted for G1; PM5 not stated; PM6 not granted (only if an incentive is offered); PM7 granted.
- **Analysis approach:** the fixed lines for M1, M3 and M6, with "records period not stated" for M6, and the blank for the result that would change the decision.
- **Limits:** the fixed limits for M1, M3 and M6; Q1 not covered for G2 by M6; both groups reached from lists the organization holds; E2 and E3 not relied on; groups of 5 so counts only. No question left uncovered.
- **Decisions (6):** the 34 h overrun; method and types; participant criteria and counts; permissions PM1 for G2 and PM5; recording and incentive; the result that would change the decision.

## What was observed

- **Every required part was produced** and no stop condition was triggered. The assistant contacted no one and stated no finding.
- **Difference from the published example:** none in substance. Every method, figure, status and decision matches. Wording differs in small places (for example the exact phrasing of the two screening questions and the limits that cover the sample basis). Both versions give 76 h, 42 h and over by 34 h.
- **Facts not in the inputs:** both plans contain a few. The screening questions choose a period ("the last four weeks") and a word for the product ("meal plan"); the inputs give neither. The example's sample-basis limit says subscribers who ignore email are absent, which is general reasoning, not an input. Neither plan states a finding.
- **Where the template was ambiguous and a guess was needed:**
  1. The 5 participants per group for M1 and M3 are counted separately, so 20 sessions' worth of people. The template does not say whether the same person may take part in both. The hours assume they do not.
  2. M6 has no participants, so "hours per participant" has nothing to print for it. The plan prints M1 and M3 only.
  3. The length of the period in a screening question is left to the assistant ("a stated period"). "At least weekly" was turned into "all four of the last four weeks"; whether three of four should qualify is the research lead's call, and the plan does not say so.
  4. Decision step (d) says "each permission", while the header counts decisions. The assistant printed PM1 for G2 and PM5 together as one decision, giving 6. Printed one each, the count would be 7. PM3 and PM6 are also not stated or not granted but are treated under the recording and incentive decision because they are conditional.
  5. The incentive setting says "undecided" while PM6 says "not granted". The template does not say which governs.
  6. The "Prepared" line asks for "[settings]" without saying whether to list each setting or only count them.
  7. PM1 for G2 is not granted, yet G2's participants stay in the hours and the time check. The template does not say whether to show a version without G2.
  8. PM4 is granted for product analytics events, but the records period is not stated, so the plan cannot say whether the grant covers the period the research lead will choose.
  9. PM7 covers "the prototype build of the plan screen"; the inputs do not say whether it shows both the list and the grid view that Q3 asks about.
- **Shortcomings of the template found:** the points above. The acceptance tests in the template are marked "proposed, none has been run"; this trial ran only test 1 (an ordinary plan) in effect, with test 9 (a permission not granted) and test 10 in part. The stop conditions, the type F rule and the declines were not exercised.
- **Limits of this trial:** one run, in one product, on an invented example, by an assistant that had the template open. It shows the instructions can be followed to a complete plan. It does not show the plan would suit a real research lead or a real study.

## Revision note, added after review

The run recorded above was made against the first wording of the instruction block, which did not carry the analysis lines, the fixed limits, the order of the decisions or the exceptions itself. After an independent review, the block was rewritten to carry them, and the template settled several of the ambiguities listed above (one decision for all permissions, the recording and incentive settings against PM3 and PM6, a count of settings on the Prepared line, no per-participant hours for M5 and M6, different people in each method, and a group whose permission is not granted staying in the plan). The published example was adjusted to match in four small places: the Decision line now repeats the supplied question word for word, the Prepared line counts 6 settings, the hours-per-participant line says M6 has fixed hours, and the sample-basis limit no longer adds a reason that was not in the inputs. The run above was not repeated at that point, and its recorded output and observations are unchanged. The second pass below was made later.

## Second pass, on the current wording

Made on 2026-11-10, after the second review, on the instruction block and output format as they now stand. It was made by the assistant that edited the template after that review, so it is a follow-through of the current block against the same invented inputs, not an independent run. Nothing in the first record above was changed.

The edits it checks: the plan now says the research lead confirms the qualifying answers (step 5 of the block, decision (c)); decision (a) offers cutting participants as well as leaving a method out, with the hours each participant fewer saves in M1 to M4; a granted permission whose note does not clearly cover the planned use is raised in decision (d); and the example's Defaults used line and closing line were completed.

What it produced:

- **Unchanged:** the questions, evidence statuses, options, proposed set (76 h against 42 h, over by 34 h, 13.0 days against 7.0), the participant counts, the limits and the six decisions, in the same order.
- **Changed as the edits intend:** decision 1 offers the participant cut (3 h each in M1 or M3); decision 3 asks the research lead to confirm that only "All four" of the last four weeks qualifies for "at least weekly"; decision 4 and the permission lines for PM4 and PM7 now say the notes do not show whether the grant covers the records period (not stated) or whether the prototype shows both views. Observations 7 and 8 of the first run (PM4's period, PM7's views) are now raised in the plan; observation 3 is now put to the research lead.
- **Still open:** observation 7 of the first run, a version of the hours without G2 while PM1 for G2 is not granted, is still not covered by the template. The facts not in the inputs ("the last four weeks", "meal plan") are still the assistant's proposal and are now named as such at the foot of the example.
- **Limits of this pass:** one pass, by an assistant that knew the edits it was checking, on an invented example. It shows the current block can be followed to the plan published in the example. It does not show the plan would suit a real research lead.
