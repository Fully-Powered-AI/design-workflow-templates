# AI workflow templates for designers and product teams

FullyPowered Workflow Templates for design and user experience teams turn the AI your company already pays for into a team that knows how the work is done: a design-system owner with the component inventory audited and every possible overlap listed, a design lead with the current experience baseline drafted before a redesign, a research lead with the user research plan prepared for a design decision. 7 workflow templates, made to be customized and deployed. All plain Markdown, all free, MIT license.

We are FullyPowered AI. We build AI workflows for companies, and these are the templates we start from. We publish them because a good starting point should be open to everyone. Copy one. Change it. Make it yours.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** These are templates, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See more examples for design and user experience teams](https://fullypowered.ai/functions/design-and-user-experience/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-readme&from=gh-design-readme) · [Have one built for your team](https://fullypowered.ai/pricing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-readme&from=gh-design-readme). Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Who this is for**

- Heads of design and product who want AI giving their designers precise, reviewable preparation.
- Design leads and design-system owners who want a method their team can run this week.
- The designer or researcher who does the work, gets a careful draft and still makes the call.

**What these are for**

- **Your best way of doing it, for the whole team.** One piece of work, written down precisely enough that an assistant prepares it the same way every time.
- **Work you can check.** Every template says what it needs, what it produces, what it checked and what it could not.
- **A person decides.** Anything that sends, posts, pays or changes a record waits for someone to approve it.
- **Tied into your business systems.** A workflow can be designed to pull from the systems your company already runs, and even push data back into them, with guardrails and a person approving. [Browse the Connectors Directory](https://fullypowered.ai/connectors/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-readme&from=gh-design-readme).
- **Free, open and portable.** MIT-licensed plain instructions that run in the assistant or agent your team already uses: ChatGPT, Claude, Claude Code, Claude Cowork, Codex, Copilot, Gemini, Grok, Perplexity.

**Quick start**

1. **Plan a user study from one design question.** Open ChatGPT, Claude, Copilot or Gemini and paste the text below. Replace the square brackets with your own design question and what you know. Everything stays a draft until you approve it.

   ```text
   You prepare a user research plan for me, the research lead. You prepare
   and I decide. Do not contact anyone, invent a participant or a result,
   state a finding, recommend a design or send anything. My design
   question, with the date the decision is taken: [question and date]. The
   user groups, how each can be reached and roughly how many there are:
   [groups]. Evidence we already hold, with dates: [evidence or none].
   Permissions already given or refused, and who decides: [permissions or
   none]. Researcher days available: [number]. Sort my questions by type.
   Show what existing evidence covers. Offer method options with hours,
   then propose a set and check it against my time. Ask me for anything
   missing, list what the study cannot establish, and end with numbered
   decisions for me.
   ```

2. Read what comes back. It marks what it checked and what is left for you. What comes out: a plan with decisions for you:

   ```text
   USER RESEARCH PLAN: Default view of the plan screen on phones

   For: Research lead. Decision: Should the weekly plan screen open in a list view instead of a calendar grid on phones, in the redesign going to design review on 2026-12-04? To be taken 2026-12-04.
   Prepared: 2026-11-10, from the design question, 3 questions (supplied), 2 groups, 3 pieces of evidence, 8 permission lines, 6 settings. Not supplied: records period.
   Defaults used: evidence old after 12 months, cutoff 2025-11-10 (default); 6 hours to a day, shown to the next half day (default); counts rather than percentages under 20 participants (default); survey response rate 15% (default); 5 participants per group for interviews and usability sessions (default); standing exclusions X1 and X2 (default)

   WHAT WE NEED TO KNOW
   Q1 How do subscribers use the plan screen on a phone today, and how often do they switch between grid and list? | type A: what people do and how often
   Q2 Why do some subscribers switch views, or give up looking for a given dinner? | type B: why, and in what situation
   Q3 Can a person find a given evening's dinner and swap it for another, in each view, on the redesigned screen? | type C: whether people can finish a task with a given design
   Set aside: None
   ```

3. Stop there. You will know if this is for you. When you want it fitted to your company, or built into your agents, [that is what we do](https://fullypowered.ai/pricing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-readme&from=gh-design-readme).

A person starts every workflow, supplies the inputs and decides; the template only prepares and checks, and the designer or research lead approves the result.

These are samples and a starting point, made to be changed to fit how your team works. Work that is not listed here can be built too, as a single step or as many.

## The workflow templates here today

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

The [FullyPowered Workflows Directory](https://fullypowered.ai/workflows/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-readme&from=gh-design-readme) lists every workflow template across functions and industries, with search. A machine-readable list of this repository is in [index.json](index.json).

For the work these templates come from, by team and by task, see [AI workflow examples for design and user experience teams](https://fullypowered.ai/functions/design-and-user-experience/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-readme&from=gh-design-readme).

## Licence and credits

MIT, in [LICENSE](LICENSE) and in every folder. Each folder's SOURCES.md names what the workflow template drew on. Published by [FullyPowered AI](https://fullypowered.ai/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-readme&from=gh-design-readme).
