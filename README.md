# Fully Powered Workflow Templates: Design and User Experience

Design decisions that survive the handoff. These workflow templates take the planning, auditing and recording around design work and give an AI assistant a precise way to prepare it. They produce no design and certify no accessibility conformance: the designer decides.

This repository holds 7 workflow templates for designers and the product people who work with them. Each one is a single piece of work with its own folder: what it is for and who starts it, the complete template an AI assistant follows, a worked example with invented data, what to change for your company, what has been checked, and its sources.

## The workflow templates

- **[Component inventory audit](component-inventory-audit/)**: When patterns come up for review, the design-system owner gets an inventory built from the library export and its documentation: every component with its naming, token and state gaps, and the pairs that may overlap. Nothing is merged on appearance; the owner decides.
- **[Component specification](component-specification/)**: When an approved reusable component needs documenting, the design-system owner gets one specification of its variants, states, usage rules and accessibility notes, set beside the existing patterns, with every gap or clash written as a choice for the owner.
- **[Current experience baseline](current-experience-baseline/)**: Before a redesign, the design lead gets a baseline built from the captures and page list they supply: each page read with its content and design observations, the patterns that recur, and the pages outside the evidence. The lead confirms the baseline and sets the scope.
- **[Design handoff record](design-handoff-record/)**: Before engineering starts, the design owner gets one record built from the approved design: every state, token, breakpoint and content rule either covered or flagged, with each unstated behaviour written as a question. The engineer confirms the questions are resolved.
- **[Document accessibility review](document-accessibility-review/)**: Before a designed report, deck or publication goes out, the designer gets a findings list on its headings, reading order, image descriptions, tables and contrast, with every check that could not be made named. The designer verifies each finding; the publication owner approves the fixes.
- **[Journey accessibility findings](journey-accessibility-findings/)**: When a user journey is ready for accessibility review, the reviewer gets a finding list: each finding with its task impact and evidence, the manual checks still required and the limits of the review. The reviewer verifies every finding and agrees fixes with the design owner.
- **[User research plan](user-research-plan/)**: When a design decision needs user evidence, the research lead gets one study plan: what the team needs to know, what evidence already exists, method options with their hours, participant criteria, permissions needed, how answers will be read and what the study cannot establish.

## How to use one

Open a folder and start with its README. Every folder stands alone, so copy the one you want and leave the rest. The templates are written for ChatGPT, Claude, Copilot and Gemini: paste the instruction block and the output format in as custom instructions, or load the folder in a product that reads `SKILL.md` packages.

To take the whole collection, press **Use this template** at the top of this page: it copies every folder into a repository in your own account, yours to change.

In every template a person starts the work, supplies the inputs and decides. The template prepares and checks. Anything that sends, posts, pays or changes a record waits for a person to approve it.

## What SKILL.md is

Each folder holds a file named `SKILL.md`. It is the technical file: the same instructions and output format as the template, in the packaged form that AI products which load instructions from a folder read. It is generated from `TEMPLATE.md`, so the two always agree. The workflow template is the whole folder; `SKILL.md` is one way of loading it. If your AI product does not read that format, use `TEMPLATE.md`.

## What "checked" means here

Each folder says exactly what was checked and when: who wrote it, that its sources and rights were reviewed, the date of its editorial review, and whether it has been tried on its invented example in a named AI product. Nothing is described as tested for a client unless it was. Test a template on your own past work before your team relies on it; each one comes with acceptance tests for that.

## More workflow templates

The [Fully Powered Workflows Directory](https://fullypowered.ai/workflows/) lists every workflow template across functions and industries, with search. A machine-readable list of this repository is in [index.json](index.json).

For the work these templates come from, by team and by task, see [AI workflow examples for design and user experience teams](https://fullypowered.ai/functions/design-and-user-experience/).

## Licence and credits

MIT, in [LICENSE](LICENSE) and in every folder. Each folder's SOURCES.md names what the workflow template drew on. Published by [Fully Powered AI](https://fullypowered.ai/).
