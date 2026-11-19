# Design handoff record

One record from the approved design, with every state, token and rule covered or asked as a question. The design owner answers; the engineer confirms.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** This is a template, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See Design handoff record on our website](https://fullypowered.ai/workflows/design-handoff-record/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Quick start**

1. Read EXAMPLE.md to see what a good result looks like.
2. Copy all of TEMPLATE.md into your assistant, then give it your own inputs, or the sample ones from EXAMPLE.md.
3. Read what comes back. It marks what it checked and what is left for you.

*Workflow template · Design and user experience · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/design-handoff-record/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record)*

## The outcome

A static design shows one moment of each screen. The engineer still has to build the moments it leaves out: what the button does while it is working, what the list shows when it is empty, what happens to a long name on a narrow screen. Those gaps often surface mid-build, one message at a time, and each one is answered from memory or guessed.

This workflow template puts them on one page before the build begins. For every item in the design, the record lists the states it needs, marks each as shown in the design, documented by the component, or unstated. It names the tokens the design uses with their values, the layout shown at each screen width, the rule for each piece of content, and what each control does. Every gap is a numbered question addressed to the design owner. Nothing is filled in on anyone's behalf.

The design owner answers the questions and approves the record. The engineer confirms that every question is resolved and nothing is left to inference.

## Who starts the work, and when

The design owner, or the designer who prepared the design, starts it when an approved design is ready to hand to engineering. Run it again if the design changes after handoff, with the corrected files. The engineer reads the finished record before estimating or building.

## What they supply

- An inventory of the approved design: one row per component in one state at one width, with its screen, kind, content fields and tokens. A person writes this inventory, or exports it from the design tool; the assistant reads only what is written, so for a large design it takes real work.
- The component references: which states each component documents in your design library.
- The token list: names and values.
- The content rules: longest value and what happens when a value is longer.
- The interaction decisions made so far, if any.
- A few settings: the smallest supported width, your breakpoints, and who the design owner and engineer are.

## What comes out

One record in a fixed order: items with their states and tokens, responsive behaviour by screen and breakpoint, content rules, interactions, the numbered questions for the design owner, anything set aside, and a sign-off block for the two people who decide. If a section has nothing in it, the record says None.

The record creates no design and invents no intended behaviour. Where the design says nothing, it asks.

See the worked example in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Design and user experience](https://fullypowered.ai/functions/design-and-user-experience/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record), where the approved design is the last thing the design owner controls before building starts.
- [Software engineering](https://fullypowered.ai/functions/software-engineering/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record), where the engineer needs the answers before estimating, not after the first pull request.
- [Software technology](https://fullypowered.ai/industries/software-technology/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record), where design and engineering hand work back and forth every sprint.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record), where long product names, empty carts and failed payments are the screens customers meet most.
- [Professional services](https://fullypowered.ai/industries/professional-services/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record), where an agency hands an approved design to a client's engineers.
- [Startups & new ventures](https://fullypowered.ai/situations/startups-and-new-ventures/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record), where one designer and a few engineers cannot afford a week of back-and-forth.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record), where more teams build from the same design library and the unwritten rules stop travelling by word of mouth.

It is a different piece of work from [Acceptance criteria sheet](https://fullypowered.ai/workflows/acceptance-criteria-sheet/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record), which turns one story into testable expectations, and from [Project handover readiness check](https://fullypowered.ai/workflows/project-handover-readiness-check/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record), which checks a finished project before a receiving team takes it on. This one records what an approved design says and leaves open, before anything is built. It is also separate from [Component specification](https://fullypowered.ai/workflows/component-specification/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record), which documents one approved component in full for the design library.

## What has to change for your company

Fix the column headers of your design inventory once, and decide who exports it from your design tool. Write your breakpoints and your smallest supported width into the settings. Know that breakpoint coverage is checked per screen, not per item: an item with no row in a range is not flagged, so a missing item at a width needs your own check. Decide whether your four kinds of item (static, control, field, data) and their fixed lists of states match how your design library is organised. Agree who the design owner is for each product, who answers when they are away, and where the answered record is kept for the engineer.

## What has been checked

FullyPowered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried on its example in Claude on 10 November 2026; it was run twice, and the record of the second run, which was not blind, is published with it. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a design that has already been built, with cases written in advance: a state the library documents but the design does not show, a token that is not in the list, a screen with no tablet layout, a content field with no length. The design owner checks every line against the design before anyone relies on the record. [Acceptance criteria sheet](https://fullypowered.ai/workflows/acceptance-criteria-sheet/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record) is the place to turn the answered record into checks for a story.

- Written by FullyPowered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example.
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

- [Acceptance criteria sheet](https://fullypowered.ai/workflows/acceptance-criteria-sheet/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record)
- [Project handover readiness check](https://fullypowered.ai/workflows/project-handover-readiness-check/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record)
- [Component specification](../component-specification/)

## Make it yours

This workflow template is an example and a starting point. FullyPowered AI adapts it to how your company works, proves it on real work and rolls it out to the roles that use it. We can also build any other workflow for your company, including one that runs several steps, in a Workflow Sprint or a scoped implementation. [Talk with us](https://fullypowered.ai/contact/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-design-handoff-record&from=gh-design-design-handoff-record).
