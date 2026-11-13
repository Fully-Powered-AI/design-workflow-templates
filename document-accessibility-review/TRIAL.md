# Document accessibility review: trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-11

The inputs were the invented example in [example.md](example.md): the review settings, structure list, table list, contrast list and checker report for the invented "Annual review 2026" of an invented arts charity. No client data was used. This is a second run, made after a review of the first led to changes to the instruction block and the output format (the default contrast thresholds, the exact finding wordings, what counts as one item not checked, slide counts for decks, and blank lines between findings). The first run's record is replaced by this one. The run was done by the same session that made those changes, so it was not blind: it applied the instruction block and the output format to the example's inputs only, without copying from the example's findings list, and compared the result with that list afterwards.

## Inputs used

The five inputs under "The inputs" in [example.md](example.md): 20 structure rows on 4 pages, 2 table rows, 7 contrast rows and 4 checker items.

## What came out

All parts of the output format were produced: the header, the summary counts, the findings in five areas, other observations, what could not be checked, the checker report and the closing line. Nothing in the inputs made the instructions stop. The full output follows.

```
DOCUMENT ACCESSIBILITY REVIEW: Annual review 2026, annual-review-2026-v3.pdf

For: Client K's head of communications, with the designer at Studio M. Kind: PDF. Audience: members, funders and the public. As of 2026-11-10. Accessibility reviewer: none named.
Thresholds: 4.5 to 1 for other text; 3 to 1 for large text (18 pt and above, or 14 pt and above in bold). The defaults.

Summary: 12 findings. Headings 2; reading order 1; alternative text 5; tables 2; contrast 2.
Structure list: 20 rows on 4 pages: 4 heading, 7 paragraph, 0 list, 5 figure, 2 table, 2 artifact.
Tables described: 2 of 2. Contrast rows: 7: 2 below your threshold, 3 at or above, 1 varies, 1 not measured.
Not checked here: 5 items, listed under WHAT COULD NOT BE CHECKED. Other observations: 1. Checker items: 4.

FINDINGS

Headings
H1. Page 2, seq 8, "Where the money came from"
Rule: looks like a heading but is marked as a paragraph.
From the list: marked paragraph; visual role heading.
Question for the designer and the publication owner: Does the designer confirm H1 in the file, and what correction does the publication owner approve?

H2. Page 3, seq 10, "Programmes"
Rule: skipped level: level 4 follows level 2 at seq 5.
From the list: marked heading, level 4; visual role heading.
Question for the designer and the publication owner: Does the designer confirm H2 in the file, and what correction does the publication owner approve?

Reading order
R1. Page 3
Rule: read earlier than intended.
From the list: the structure reads seq 10, 11, 12, 13, 14 in intended order 1, 2, 5, 3, 4. Read early: seq 12, "Pull quote: I found my people here" (intended 5).
Question for the designer and the publication owner: Does the designer confirm R1 in the file, and what correction does the publication owner approve?

Alternative text
A1. Page 1, seq 3, "Cover photo of a summer workshop" (image)
Rule: alternative text is a file name.
From the list: marked figure; alternative text "IMG_0042.jpg".
Question for the designer and the publication owner: Does the designer confirm A1 in the file, and what correction does the publication owner approve?

A2. Page 2, seq 9, "Pie chart of income by source" (chart)
Rule: alternative text is only a general word; chart description gives no figures.
From the list: marked figure; alternative text "Pie chart".
Question for the designer and the publication owner: Does the designer confirm A2 in the file, and what correction does the publication owner approve?

A3. Page 3, seq 15, "Photo of children painting a mural" (image)
Rule: informative image marked as decorative, so screen readers skip it.
From the list: marked artifact; alternative text none.
Question for the designer and the publication owner: Does the designer confirm A3 in the file, and what correction does the publication owner approve?

A4. Page 4, seq 18, "Decorative swirl" (decorative)
Rule: decorative image is read aloud.
From the list: marked figure; alternative text "decorative swirl".
Question for the designer and the publication owner: Does the designer confirm A4 in the file, and what correction does the publication owner approve?

A5. Page 4, seq 19, "Contact box with address and phone number" (image of text)
Rule: text set as an image.
From the list: marked figure; alternative text "Contact us".
Question for the designer and the publication owner: Does the designer confirm A5 in the file, and what correction does the publication owner approve?

Tables
T1. Page 3, seq 13, table TB1, "Attendance by programme"
Rule: row labels in the first column not marked as headers.
From the list: marked table; visual role table; header row marked yes; first column holds labels yes; first column marked no; merged cells yes.
Question for the designer and the publication owner: Does the designer confirm T1 in the file, and what correction does the publication owner approve?

T2. Page 4, seq 20, table TB2, "Footer in two columns: address and charity number"
Rule: marked as a table but laid out as text: a layout table.
From the list: marked table; visual role text.
Question for the designer and the publication owner: Does the designer confirm T2 in the file, and what correction does the publication owner approve?

Contrast
C1. Page 1, pair K2, Subtitle on the cover
Rule: below your threshold.
From the list: 3.9 to 1, measured with Contrast tool A; 14 pt, not bold, so other text; your threshold 4.5 to 1.
Question for the designer and the publication owner: Does the designer confirm C1 in the file, and what correction does the publication owner approve?

C2. Page 3, pair K6, Table text on shaded rows
Rule: below your threshold.
From the list: 4.4 to 1, measured with Contrast tool A; 9 pt, not bold, so other text; your threshold 4.5 to 1.
Question for the designer and the publication owner: Does the designer confirm C2 in the file, and what correction does the publication owner approve?


OTHER OBSERVATIONS

Page 4, seq 17, "Our funders: Funder A; Funder B; Funder C": marked paragraph; visual role list. Question: does the designer treat this as a finding, or set it aside?

WHAT COULD NOT BE CHECKED

Descriptions for a person to confirm: seq 7, page 2, "The chair standing in the main gallery". Does each carry what the reader needs from the image?
Pages whose reading order was not checked: page 1 (seq 4 has no intended order).
Tables not described or marked unknown: none.
Merged cells to hear read aloud: TB1, page 3.
Contrast that varies across its background: K1, page 1, Title over the cover photo.
Contrast not measured: K7, page 4, Charity number in the footer.
Never covered by this review: how the file behaves with a screen reader or other assistive software; link wording; form fields; colour used alone to carry meaning; captions, transcripts and audio description for media; the document's language and title settings; and anything not in the lists supplied.
This is a findings list for the designer to verify. It states no conformance with any standard and declares no part of Annual review 2026 accessible.

CHECKER REPORT

Checker items: 4: 2 matched to findings, 0 with no finding there, 1 naming no page, 1 outside the five areas.
1. "Alternate text: page 1, figure alternate text may be a file name": see A1.
2. "Headings: page 2, text styled as a heading is not tagged as one": see H1.
3. "Primary language: not set": outside the five areas of this review.
4. "Reading order: needs manual check": names no page; the designer matches it by hand.
A checker that reports nothing is not taken as a pass for any area.

Every finding traces to a row in the lists supplied, as of 2026-11-10. The review changes no file and sends nothing; the designer verifies each finding, and the publication owner approves the corrections and decides on the release.
```

## What was observed

- **Every required part was produced,** and every figure in the summary recounted correctly against the lists: 12 findings (2 headings, 1 reading order, 5 alternative text, 2 tables, 2 contrast), 5 items not checked, 1 other observation, 4 checker items.
- **The output matches the published example** in every finding, every count, every placing of a checker item, the wording of each rule and the blank lines between findings, except that the recorded output has two blank lines before OTHER OBSERVATIONS where the example has one.
- **The thresholds came from the block alone.** The settings said "the defaults"; the block's step 7 gave 4.5 to 1 and 3 to 1, which produced the Thresholds line, the two findings below the line (3.9 and 4.4), the three at or above (including 4.5 for 12 pt bold text and 3.4 for 20 pt text) and the large-text label for the pull quote.
- **The count of items not checked was no longer a guess.** Counting each listed item once on the first six lines (one description, one page, one merged-cell table, one varying pair, one unmeasured pair) gave 5, as the block now says.
- **Still true, and now stated in the template:** a blank intended order on page 1 leaves that whole page's reading order unchecked, and a figure that looks decorative (seq 18) is left out of the reading order and raised under alternative text only. This run did not test the new slide-count rule for decks, because the example is a PDF.
- **No fact appears in the output that is not in the inputs.** Content and alternative text are quoted as supplied.
- **What this trial does not show.** It was one run, in one product, on a small invented document, by the session that edited the template. It did not test the fifteen acceptance tests in the template, which still describe themselves as proposed. It says nothing about a real document, a real designer's lists or a larger file. The designer's check of each finding in the file was not tested.
