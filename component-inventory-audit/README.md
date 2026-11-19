# Component inventory audit

Get an inventory of every component in your design library with naming, token and state gaps and possible overlaps. The owner decides.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** This is a template, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See Component inventory audit on our website](https://fullypowered.ai/workflows/component-inventory-audit/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Quick start**

1. Read EXAMPLE.md to see what a good result looks like.
2. Copy all of TEMPLATE.md into your assistant, then give it your own inputs, or the invented ones from EXAMPLE.md.
3. Read what comes back. It marks what it checked and what is left for you.

*Workflow template · Design and user experience · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/component-inventory-audit/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit)*

## The outcome

The design-system owner opens a review with one list of every component in the library, instead of a file tree, a documentation site and a token file read side by side. Each component shows its category, status, variants, documented states and the tokens it uses. Against it sit the gaps, numbered: a name that breaks your convention, a token the token file does not define, a state your standard requires that nobody documented.

The audit also names pairs of components that may be the same pattern drifting apart, and says which signals made it think so. It does not say they are the same. Two components with different names can serve different uses, so each pair arrives with both documented purposes side by side and a blank for your decision: consolidate, keep or investigate.

The assistant changes no library, proposes no new design and gives no view on how anything looks. The owner decides.

## Who starts the work, and when

The design-system owner, or a design operations lead working for them, starts it when the library's patterns come up for review: a scheduled audit, a quarter's cleanup, a merger of two products' libraries, or the moment a new team asks why there are two buttons. It can be run again after fixes to see what remains open.

Frontend engineers and designers answer questions about particular components. The owner makes every decision the audit sets up.

## What they supply

- **Audit settings:** the library's name, the owner, the export date, your component naming rule, your token naming rule, the states every component must document and any category that needs a different list.
- **The component export** as a file: one row per component, with its category, status, documented purpose, variants, documented states, tokens used and documentation reference.
- **The current token definitions** as a file: each token's name, value, type and status.

Both files are text exports from your own library. No connection to a design tool or code repository is needed, images are not read, and the workflow template never asks for a password, a login code or a key.

## What comes out

One inventory in a fixed order: a summary with counts, one line per component, a numbered list of naming, token, state and documentation gaps, notes on the token file itself, and a list of possible overlaps. Each possible overlap shows the signals that matched, both documented purposes, the differences the export does show, and a slot for the owner's decision.

Where a section has nothing in it, it says so in words rather than being left out.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Design and user experience](https://fullypowered.ai/functions/design-and-user-experience/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit), where a design system is only as useful as it is consistent.
- [Software engineering](https://fullypowered.ai/functions/software-engineering/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit), where the same pattern coded twice becomes two things to maintain.
- [Product management](https://fullypowered.ai/functions/product-management/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit), where a roadmap needs to know what the interface is already built from.
- [Software and technology](https://fullypowered.ai/industries/software-technology/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit), where product teams add components faster than anyone reviews them.
- [Ecommerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit), where storefront, checkout and campaign teams often grow their own variants.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit), where agencies keep brand libraries for several clients at once.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit), when more teams are building on the library than the owner can follow.
- [Acquisitions & integration](https://fullypowered.ai/situations/acquisitions-and-integration/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit), when two products' libraries have to be compared before anyone decides what to keep.

It checks a design library's components, names, tokens and states. It does not check a spreadsheet before it is shared ([spreadsheet check before sharing](https://fullypowered.ai/workflows/spreadsheet-check-before-sharing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit)), describe what a data export contains ([dataset profile](https://fullypowered.ai/workflows/dataset-profile/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit)) or review a website's findability ([website findability audit](https://fullypowered.ai/workflows/website-findability-audit/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit)).

## What has to change for your company

- **Your naming rules.** Choose the component naming rule your library follows, and the token naming rule, or accept the defaults.
- **Your required states.** List the states every component must document, and give a different list for categories such as inputs.
- **Your qualifier words.** Words such as old, new and copy in a name usually mean a version was never retired. Add or remove words for your own habits.
- **Your status words.** Say which word in your export means deprecated and which means experimental.
- **Your columns.** Use the column names your tools export, or rename them once to the defaults. When a header does not match, the assistant stops and asks.
- **Your owners.** Decide who answers for each category and who makes the final call on consolidation.

## What has been checked

FullyPowered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026; the record of that run is published with it. It has not yet been tested in a client environment, or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a library the owner already knows well, with cases written in advance: a name that breaks the rule, a token that was deleted but is still used, a component with no documented states, two components that really are different, and two that really are the same. The owner checks every gap and every pair against the library itself before anyone relies on the inventory. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit) describes the record we keep.

- Written by FullyPowered AI.
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

- [Spreadsheet check before sharing](https://fullypowered.ai/workflows/spreadsheet-check-before-sharing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit)
- [Dataset profile](https://fullypowered.ai/workflows/dataset-profile/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit)
- [Website findability audit](https://fullypowered.ai/workflows/website-findability-audit/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit)

## Make it yours

This workflow template is an example and a starting point. FullyPowered AI adapts it to how your company works, proves it on real work and rolls it out to the roles that use it. We can also build any other workflow for your company, including one that runs several steps, in a Workflow Sprint or a scoped implementation. [Talk with us](https://fullypowered.ai/contact/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-component-inventory-audit&from=gh-design-component-inventory-audit).
