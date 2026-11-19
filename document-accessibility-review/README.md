# Document accessibility review

A findings list for a designed report, deck or publication: headings, reading order, image descriptions, tables and contrast, and what went unchecked.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** This is a template, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See Document accessibility review on our website](https://fullypowered.ai/workflows/document-accessibility-review/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review) Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Quick start**

1. Read EXAMPLE.md to see what a good result looks like.
2. Copy all of TEMPLATE.md into your assistant, then give it your own inputs, or the invented ones from EXAMPLE.md.
3. Read what comes back. It marks what it checked and what is left for you.

*Workflow template · Design and user experience · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/document-accessibility-review/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review)*

## The outcome

A finished document that more of its readers can actually use. Annual reports, client decks, press packs and campaign brochures are designed to be seen, and the parts a screen reader relies on are easy to miss: a heading that only looks like one, a photo the file hides, a sidebar read before the story it sits in, a table whose row labels are announced as plain cells, grey text a little too pale on a shaded panel.

This workflow template takes the designer's own lists of how the file is built and turns them into one findings list in five fixed areas: headings, reading order, alternative text, tables and contrast. Every finding names the page, the element, the rule it breaks and the rows it comes from, and ends with the same plain question for the designer and the publication owner.

It is just as clear about what it did not check. Whether an image description says the right thing, how merged table cells sound, text over a photograph and anything never measured are listed by name, and so are the things this review never covers. A clean result from an automated checker is never treated as a pass. The list certifies nothing and declares nothing accessible: a person verifies, and a person decides.

## Who starts the work, and when

The designer who built the document, or the production lead, starts it when a designed document, deck or publication is ready to hand over or release. For an agency, that is before the client handoff; for a publisher or a charity, before the file goes to readers.

The designer prepares the lists from the file and verifies every finding. Where the team has an accessibility reviewer, that person verifies instead. The publication owner, on the client's side where there is a client, approves the corrections and decides when the document goes out.

## What they supply

- **The review settings:** the document's title and file name, its kind (PDF, word-processor document, slide deck, or web page or email), the number of slides for a deck, the audience, the as-of date, who the designer and the publication owner are, and the contrast thresholds if the team has its own.
- **A structure list:** one row per element in the order the file presents it, saying how the file marks it, what it looks like on the page, its heading level, where the designer means it to be read (every element a screen reader reaches needs this, or its page's reading order cannot be checked), its first words and its alternative text.
- **A table list:** for each table, whether the header row and the row labels are marked, and whether it has merged cells.
- **A contrast list:** each text and background pair measured with a contrast tool, with the text size, whether it is bold and the ratio the tool reported.
- **The checker report,** if an automated checker was run: its items, pasted as they are.

The lists come from the views the document tool already offers and a contrast tool. Preparing the lists is the main effort, and it grows with the number of elements in the document. If time is short, start with the pages that carry images and tables, and run the review on those pages; it covers only what is supplied. No connection to the design tool, the file store or any account is needed, and no sign-in details are asked for. When a header in a list does not match the expected column names, the assistant stops and asks.

## What comes out

One findings list in a fixed order: a summary with every count, numbered findings under headings, reading order, alternative text, tables and contrast, other observations, everything that could not be checked, and the checker's items placed against the findings.

Good looks like this: the designer can open any finding, go to the page and element it names and see exactly what to confirm in the file. Every figure in the summary adds up from the lists, nothing is added that the lists do not say, and no correction is written for anyone. The designer proposes the fixes and the publication owner approves them.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Design and user experience](https://fullypowered.ai/functions/design-and-user-experience/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review), where the designer checks the file before it leaves the studio.
- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review), which owns the reports, guides and brochures that carry the brand to every reader.
- [Marketing and advertising](https://fullypowered.ai/industries/marketing-and-advertising/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review), where a campaign deck or brochure is checked before the client handoff.
- [Media and entertainment](https://fullypowered.ai/industries/media-and-entertainment/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review), where a digital feature, press pack or companion document goes to every kind of reader.
- [Nonprofits](https://fullypowered.ai/industries/nonprofits/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review), where an annual review or appeal pack has to reach members and funders who read with assistive software.
- [Education](https://fullypowered.ai/industries/education/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review), where course handbooks and slide decks have to work for every learner.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review), with a steady flow of reports and decks built from the same templates.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review), when more documents go out than anyone has time to check by hand.

It reviews one document. A task that runs across several screens of a website or app, such as signing up or paying, is a different piece of work ([journey accessibility findings](https://fullypowered.ai/workflows/journey-accessibility-findings/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review)), and so is checking print artwork against product facts ([packaging artwork handoff check](https://fullypowered.ai/workflows/packaging-artwork-handoff-check/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review)).

## What has to change for your company

- **Your thresholds.** The template starts from contrast thresholds many teams use and a common rule for what counts as large text. Put your own in the settings if your team has agreed different ones.
- **Your lists.** Decide which view of each document tool your designers use for the structure order, the image descriptions and the tables, and which contrast tool they use. Rename your columns once to match the template.
- **Your areas.** Five are built in. Add another, such as link wording, only with its own column and its own rule.
- **Your general words.** The template treats a description like "image" or "chart" as empty. Add the words your documents use, in each language you publish in.
- **Your owners.** Decide who verifies, who approves corrections and who decides on the release, for your own documents and for client work.
- **Your platform.** It is written for ChatGPT, Claude, Copilot or Gemini and works from files you supply. Decide which files the assistant may read.

## What has been checked

FullyPowered AI wrote this workflow template. It was editorially reviewed on 11 November 2026. It was tried once on its invented example in Claude on 11 November 2026, and the record is published with it. It has not yet been tested in a client environment or as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a document your designer has already corrected, with cases written in advance: a heading marked as body text, an image hidden as decoration, a sidebar read out of place, a contrast ratio exactly on the threshold, and a file supplied without its lists. The designer checks every finding in the file before anyone relies on it. This workflow template certifies no conformance with any standard, gives no view on legal duties and writes no corrections.

- Written by FullyPowered AI.
- Sources and rights reviewed.
- Editorially reviewed on 11 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 11 November 2026. The record is in [TRIAL.md](TRIAL.md).
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

- [Journey accessibility findings](../journey-accessibility-findings/)
- [Design handoff record](../design-handoff-record/)
- [Packaging artwork handoff check](https://fullypowered.ai/workflows/packaging-artwork-handoff-check/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review)

## Make it yours

This workflow template is an example and a starting point. FullyPowered AI adapts it to how your company works, proves it on real work and rolls it out to the roles that use it. We can also build any other workflow for your company, including one that runs several steps, in a Workflow Sprint or a scoped implementation. [Talk with us](https://fullypowered.ai/contact/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=design-document-accessibility-review&from=gh-design-document-accessibility-review).
