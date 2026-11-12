# Component specification

When an approved reusable component needs documenting, the design-system owner gets one specification of its variants, states, usage rules and accessibility notes, set beside the existing patterns, with every gap or clash written as a choice for the owner.

*Workflow template · Design and user experience · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflow templates/component-specification/)*

## The outcome

A component that has been approved in a design is not yet a pattern anyone can use. Engineers need to know which variants exist, which states each one has, when to reach for it and when not to, and what it must do for people using a keyboard or a screen reader. If that lives in a designer's head or a comment thread, each team builds its own reading of it.

This workflow template turns the approved design into one specification. Every variant is listed with the states the design actually shows and the tokens it names. Usage rules and accessibility notes come only from what the design owner's team has written down. The specification then compares the component with the patterns already in your library and says where it overlaps and how it differs.

Anything missing is a numbered choice: a state your standard requires that the design does not show, a usage or accessibility topic nobody has written about, a clash with an existing pattern. The owner makes each choice. The workflow template invents no state, writes no rule of its own and creates or alters no component.

## Who starts the work, and when

The design-system owner, or a designer working for them, starts it when an approved component design is ready to be documented or an existing pattern is to be extended. The owner approves the finished specification together with the engineer who will implement it. Run it again when the design or the choices change.

## What they supply

- The approved design of the component as a list: one row per variant in one state, with a plain description of what the design shows and the tokens it names.
- The existing patterns in your library: name, purpose, contexts, variants, states, usage rule and reference.
- Usage and accessibility notes already written for the component, each filed under a topic.
- Engineering constraints, if any.
- A few settings: the component and library, its intended contexts and purpose, the states your standard requires, and who the owner and engineer are.

## What comes out

One specification in a fixed order: the component's purpose and contexts, its variants and states, usage rules, accessibility notes, engineering constraints, a comparison with each existing pattern, the numbered choices for the owner, anything set aside, and a sign-off block for the owner and the engineer. If a section has nothing in it, it says None.

It does not recommend which choice to make. A person makes it.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Design and user experience](https://fullypowered.ai/functions/design-and-user-experience/), where a reusable component is only reusable once it is written down.
- [Software engineering](https://fullypowered.ai/functions/software-engineering/), where the implementing engineer needs variants, states and rules in one place.
- [Software technology](https://fullypowered.ai/industries/software-technology/), where product teams add components faster than anyone documents them.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where storefront and checkout teams often need their own variant of a shared pattern.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/), where agencies maintain brand libraries and need each pattern spelled out for the next team.
- [Startups & new ventures](https://fullypowered.ai/situations/startups-and-new-ventures/), where the first design system is written down for the first time.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), where more teams build on the library and unwritten rules stop travelling.

It documents one approved component. It is a different piece of work from [Design handoff record](https://fullypowered.ai/workflows/design-handoff-record/), which records every state, token and breakpoint of a whole approved design before the build, and from [Component inventory audit](https://fullypowered.ai/workflows/component-inventory-audit/), which lists every component in a library and its gaps. Once the choices are made, [Acceptance criteria sheet](https://fullypowered.ai/workflows/acceptance-criteria-sheet/) can turn the specification into checks for a story.

## What has to change for your company

Fix the column headers of your design list and your pattern list once, and decide who exports them. Write the states your standard requires for a component. Decide whether the four usage topics and six accessibility topics match how your library documents patterns. Agree who the design-system owner is for each product, who answers when they are away, and where the approved specification is kept for the engineer.

## What has been checked

Fully Powered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried once on its invented example, in Claude on 10 November 2026, and the record is published with it. It has not been tested in a client environment or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a component that is already documented, with cases written in advance: a required state the design does not show, a topic with no note, a pattern that shares a context with the new component, a constraint that names a variant that does not exist. The owner checks every line against the design and the library before anyone relies on the specification.

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

- [Design handoff record](../design-handoff-record/)
- [Component inventory audit](../component-inventory-audit/)
- [Acceptance criteria sheet](https://fullypowered.ai/workflow templates/acceptance-criteria-sheet/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
