# Journey accessibility findings

When a user journey is ready for accessibility review, the reviewer gets a finding list: each finding with its task impact and evidence, the manual checks still required and the limits of the review. The reviewer verifies every finding and agrees fixes with the design owner.

*Workflow template · Design and user experience · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflow templates/journey-accessibility-findings/)*

## The outcome

A review of a whole task, not a pile of notes. The reviewer has walked a journey, such as finding a product and reserving it, and written down what they saw. This workflow template turns those notes into one list in a fixed order: each finding names the step, the element, the agreed criterion it bears on, what it did to the person's task, and what the evidence is.

The list is honest about its own reach. A finding that rests only on an automated check or a static design file is marked as not yet observed by a person. Every step shows which hands-on checks were done and which are still owed. The review ends with its limits: what was looked at, with which software, and what was never run.

It never says a page passes, never gives a conformance rating and never redesigns anything. It sets out what the evidence shows and what the reviewer and design owner still have to settle.

## Who starts the work, and when

The accessibility reviewer starts it when a user journey is ready for review: the pages are built, or the design files are complete enough to read. The design owner is the person the findings go to, and agrees with the reviewer which fixes to make and who retests them.

The reviewer does the hands-on checking and writes the observations. The assistant organizes them. Engineers change the product only after the reviewer and design owner have agreed a fix.

## What they supply

- **The review settings:** the journey and the task a person is trying to finish, the as-of date, and who the reviewer and design owner are.
- **The journey steps,** in order, each with the page or screen and whether it is a live page, a built prototype or a static design.
- **The agreed criteria,** each with a short code, its wording and the kind of check that settles it (keyboard, screen reader, zoom or contrast).
- **The evidence,** one row per observation: the step, the kind of evidence (a keyboard walkthrough, a screen-reader walkthrough, a zoom check, a contrast measurement, a reading of the page markup or a design file, or an automated check), the element, what the reviewer used, the criterion it bears on, whether it worked, what it did to the task, and what was seen.

No connection to the live product, the design tool or any account is needed, and no sign-in details are asked for. The assistant reads only the files supplied.

## What comes out

One document in a fixed order: a summary of the findings by task impact, the journey step by step with the hands-on checks done and owed, numbered findings, observations that did not become findings, and the limits of the review.

Good looks like this: the design owner can open any finding, see the evidence row behind each statement, and know exactly what the reviewer is being asked to confirm. Every observation the reviewer supplied is accounted for, and nothing is added that the reviewer did not observe.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Design and user experience](https://fullypowered.ai/functions/design-and-user-experience/), where a journey is reviewed as a whole before it is released.
- [Software engineering](https://fullypowered.ai/functions/software-engineering/), which receives agreed fixes with the evidence behind them.
- [Product management](https://fullypowered.ai/functions/product-management/), where the owner of a journey needs to see what stands between a person and the end of the task.
- [Software technology](https://fullypowered.ai/industries/software-technology/), where sign-up and account journeys change often.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where search, choose, pay and confirm is a journey whose failure costs sales.
- [Education](https://fullypowered.ai/industries/education/), where enrolment and course journeys must work for every learner.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when journeys multiply faster than anyone can review them.
- [New business lines](https://fullypowered.ai/situations/new-business-lines/), when a new service launches with journeys no one has yet walked with a keyboard.

It is not a check of one form's fields ([lead form field review](https://fullypowered.ai/workflows/lead-form-field-review/)), and it is not a test with participants ([usability test session plan](https://fullypowered.ai/workflows/usability-test-session-plan/)).

## What has to change for your company

- **Your criteria.** Agree the list before the review starts and give each a code. The assistant uses only that list; anything else the reviewer notices is reported separately, not as a finding.
- **Your evidence file.** Use the column names given in the template, or rename yours once to match. When a header does not match, the assistant stops and asks.
- **Your checks.** The template tracks four hands-on checks per step: keyboard, screen reader, zoom and contrast. Change the set to the checks your reviewer actually runs.
- **Your impact words.** Four task-impact labels are built in. Rename them if your team already uses others, keeping their order.
- **Your owners.** Decide who confirms a finding, who agrees the fix, who retests and who may ask engineers to change the product.
- **Your platform.** It is written for ChatGPT, Claude, Copilot or Gemini and works from files you supply. Decide which files the assistant may read.

## What has been checked

Fully Powered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026, and the record is published with it; the run was read blind to the published output. It has not yet been tested in a client environment or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a journey your reviewer has already walked, with cases written in advance: a finding that rests only on an automated check, a step that exists only as a static design, a row that does not say how it was observed, an observation outside the agreed criteria. The reviewer checks every finding against the evidence row before anyone relies on it. This workflow template certifies no conformance, gives no view on legal duties and redesigns nothing.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the workflow template drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related workflow templates

- [Usability test session plan](https://fullypowered.ai/workflow templates/usability-test-session-plan/)
- [Component inventory audit](../component-inventory-audit/)
- [Lead form field review](https://fullypowered.ai/workflow templates/lead-form-field-review/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
