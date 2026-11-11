# User research plan

When a design decision needs user evidence, the research lead gets one study plan: what the team needs to know, what evidence already exists, method options with their hours, participant criteria, permissions needed, how answers will be read and what the study cannot establish.

*Capability template · Design and user experience · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/user-research-plan/)*

## The outcome

Design teams often start a study because a study is the thing to do, then find at the readout that it could not answer the question they had. This capability turns the question into a plan before anyone is invited to anything. It splits the decision into the few things the team needs to know, sorts each by the kind of answer it needs, and checks what the team already holds so that nothing is learned twice.

For each open question it lays out the methods that could answer it, with the hours each would take against the researcher time you have. It proposes the lowest-hour set, shows how far that set is over or under the time available, and says what each omission would leave unanswered. Participant criteria, a plain screening question for each, the permissions the study depends on and how the answers will be read are all written down before fieldwork. The plan includes a section that most plans leave out: what this study cannot establish.

The research lead chooses the method, approves the participants and settles the permissions. The plan changes nothing and states no finding.

## Who starts the work, and when

The research lead, or the designer or product owner working with them, starts it when a design decision is waiting on evidence and the team has not yet settled how to get it. Run it again when the question changes, when a permission is granted or refused, or when the time available moves.

## What they supply

- The design question, with the decision it feeds and the date the decision is taken. Optionally, the sub-questions in your own words.
- The user groups: who they are, how they can be reached, whether you hold usage records for them, roughly how many there are, and any must-have and must-not-have criteria.
- The evidence you already hold: what it is, its date, which groups and questions it covers, and whether it came from people who chose to speak up.
- The permissions already given or refused, and who decides each.
- A few settings: researcher days available, how old evidence may be before it is treated as old, and any defaults you want changed.

## What comes out

One plan in a fixed order: the questions and their types, the state of existing evidence, method options by question, the proposed set with its hours against the time available, participants with screening questions, permissions needed with their status, the analysis approach, what the study cannot establish, and numbered decisions for the research lead. A section with nothing in it says None.

The plan recruits no one, contacts no participant and states no finding. Where something is missing it asks; it never fills the gap.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Design and user experience](https://fullypowered.ai/functions/design-and-user-experience/), where the research lead decides what evidence the next design choice rests on.
- [Product management](https://fullypowered.ai/functions/product-management/), where the product owner needs to know what a study can and cannot settle before committing researcher time.
- [Software technology](https://fullypowered.ai/industries/software-technology/), where a redesign or a new flow is waiting on a decision about how people actually behave.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where checkout, search and account screens carry many decisions and customers are easy to reach and easy to over-sample.
- [Finance and investment](https://fullypowered.ai/industries/finance-and-investment/), where an app's users hold sensitive accounts and permissions have to be settled before anyone is approached.
- [Startups & new ventures](https://fullypowered.ai/situations/startups-and-new-ventures/), where one researcher has a few days and every one of them has to answer something.
- [New business lines](https://fullypowered.ai/situations/new-business-lines/), where the user groups are new and little evidence exists yet.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), where more teams want studies than the research lead can run, and the plans need a common shape.

It is a different piece of work from [Usability test session plan](https://fullypowered.ai/capabilities/usability-test-session-plan/), which plans the sessions once usability testing has been chosen as the method; from [Customer interview synthesis](https://fullypowered.ai/capabilities/customer-interview-synthesis/), which reads notes from conversations that have already happened; and from [Analysis plan](https://fullypowered.ai/capabilities/analysis-plan/), which prepares the analysis of a dataset in a spreadsheet. This one comes first: it chooses what kind of study the question calls for.

## What has to change for your company

Check the method menu against what your team can actually run, and change the default hours to match how long your studies take. Set how old evidence may be before it counts as old. Decide who holds each of the seven permissions in your company and where a granted permission is recorded. Agree who the research lead is for each product, and who approves the plan when they are away. Write down your standing exclusions, such as staff, suppliers and people who took part in a study recently, and where the participant log lives.

## What has been checked

Fully Powered AI wrote this capability template. It was editorially reviewed on 10 November 2026. It was tried on its invented example in Claude on 10 November 2026: a first run on the earlier wording of the instructions, then a second pass on the current wording by the assistant that made the edits, so not an independent run. The record of both is published with the example. It has not yet been tested in a client environment, or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a study your research lead has already planned, with cases written in advance: a question that no listed method can answer, evidence that is old, a group with no way to be reached, a permission that has been refused, and more hours than the time available. The research lead checks every line against the inputs before anyone relies on the plan. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete capability template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the capability drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related capabilities

- [Usability test session plan](https://fullypowered.ai/capabilities/usability-test-session-plan/)
- [Customer interview synthesis](https://fullypowered.ai/capabilities/customer-interview-synthesis/)
- [Analysis plan](https://fullypowered.ai/capabilities/analysis-plan/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
