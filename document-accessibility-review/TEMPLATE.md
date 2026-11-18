# Document accessibility review

Workflow template, version 0.1.0.

## Purpose

Turn the designer's lists of how one finished document is built into a findings list in five fixed areas: headings, reading order, alternative text, tables and contrast. Each finding names the page, the element, the rule it breaks and the rows behind it. The list also names everything the review could not check, such as whether an image description carries the right meaning, and maps any checker report onto the findings. The assistant compares the lists; it never opens or edits the file, certifies conformance with any standard, gives a view on legal duties, writes the corrections or sends anything.

## When to use it and when not to

Use it when a designed document is ready for handover or release: a PDF report, a word-processor document, a slide deck, or a web page or email built as a single publication. Run it again on the corrected file, with fresh lists, to see what is still open.

Do not use it:

- to review a task that runs across several screens of a website or app, such as signing up or paying (journey accessibility findings does that);
- to check print artwork against product facts or printer specifications (packaging artwork handoff check);
- to review captions, transcripts or audio description for video and audio. The review names them as not covered;
- to say that a document passes, conforms or is accessible. The person who verifies the findings decides that, on checks this workflow template does not run;
- to advise on legal duties or risk. That is for the organization's own advisers.

## Roles

- **Runs it:** the designer who built the document, or the production lead.
- **Prepares the lists from the file:** the designer, using the document tool's structure, reading-order, image-description and table views and a contrast tool.
- **Verifies every finding in the file:** the designer, or the accessibility reviewer where the team has one.
- **Approves the corrections and the release:** the publication owner (for a client, the client's owner of the document).
- **Makes the corrections:** the designer, only after the publication owner approves them.

## Inputs

The assistant works from the lists and notes the person supplies. It needs no connection to any design tool, file store or account, and it never asks for a password or a login code.

1. **Review settings.** The document's title; its version or file name; its kind, one of `PDF`, `word-processor document`, `slide deck` or `web page or email`; for a slide deck, the number of slides; the organization; the audience; the as-of date; the designer; the publication owner; the accessibility reviewer, if any; and the contrast thresholds, if the team uses its own. If the title, the kind or the as-of date is missing, or the kind is `slide deck` and the number of slides is missing, stop and ask. A missing name is written "not stated"; a missing reviewer is written "none named". Default thresholds: 4.5 to 1 for other text and 3 to 1 for large text, where large text is 18 pt and above, or 14 pt and above in bold.
2. **Structure list (structure.csv),** one row per element. Default headers: `seq,page,element_type,visual_role,heading_level,intended_order,content,alt_text`.
   - `seq` is a whole number: the element's place in the order the file's structure presents it. That is the tag order in a PDF, the document order in a word-processor file, the object reading order on each slide of a deck, and the source order of a web page or email.
   - `page` is the page or slide number.
   - `element_type` is how the file marks the element: `heading`, `paragraph`, `list`, `figure`, `table` or `artifact` (marked as decorative or background, so screen readers skip it).
   - `visual_role` is what a sighted reader sees, entered by the designer: `heading`, `text`, `list`, `image`, `chart`, `image of text`, `table` or `decorative`.
   - `heading_level` is 1 to 6 for a row marked `heading`, and blank for every other row.
   - `intended_order` is the place the designer means the element to be read on its page, 1 for the first. It is blank for decorative elements.
   - `content` is the first words of the text, or a short note on what an image or table shows.
   - `alt_text` is the alternative text exactly as the file holds it, for rows marked `figure`; blank when the file holds none.
   If the list is missing, stop. If only the document itself is supplied, stop and ask for the list: a reading of the visible pages cannot show how the file is marked.
3. **Table list (tables.csv),** one row per element marked `table`. Default headers: `table_id,seq,page,header_row_marked,first_column_holds_labels,first_column_marked,merged_cells`. The last four columns take `yes`, `no` or `unknown`. If the list is missing and the structure list has rows marked `table`, continue and record each of them as not described.
4. **Contrast list (contrast.csv),** one row per text and background pair measured. Default headers: `pair_id,page,element,text_size_pt,bold,ratio,measured_with`.
   - `ratio` is the number a contrast tool reported, written `4.6` for 4.6 to 1; `varies` for text over a photograph or a gradient; or blank when the pair was not measured.
   - `bold` is `yes` or `no`. `text_size_pt` is a number.
   - `measured_with` names the tool. It may be blank only when the ratio is blank.
   If the list is missing, continue and write "no contrast list supplied".
5. **Checker report,** optional: the items an automated accessibility checker listed, pasted one per line. If missing, write "No checker report supplied".

If a header in any file does not match the defaults, stop and ask which column is which. Do not guess. To avoid the question, rename the columns in your own files once, to the defaults.

## The procedure

1. **Check the inputs.** Confirm the headers. Stop and ask on any of these: a repeated `seq`, `table_id` or `pair_id`; a value outside its list; a row marked `heading` without a level from 1 to 6, or any other row with a level; two rows on one page with the same intended order; a table-list row whose `seq` is not a structure row marked `table`; a ratio with a blank `measured_with`; a text size that is not a number; for a slide deck, a page number above the number of slides. Count the structure rows by `element_type`, the pages (for a slide deck, the number of slides in the settings), the table-list rows and the contrast rows.
2. **Compare how each element is marked with how it looks.** These pairs match and raise nothing: `heading` and `heading`; `paragraph` and `text`; `list` and `list`; `figure` and `image`, `chart` or `image of text`; `table` and `table`; `artifact` and `decorative`. Every other pair is a mismatch, and goes where this rule says:
   - looks like a heading, marked anything else: Headings, "looks like a heading but is marked as a [element_type]";
   - marked `heading`, looks like anything else: Headings, "marked as a heading but looks like [visual_role]";
   - looks like an image, chart or image of text, marked `artifact`: Alternative text, "informative image marked as decorative, so screen readers skip it";
   - looks decorative, marked `figure`: Alternative text, "decorative image is read aloud";
   - looks like a table, marked anything else: Tables, "looks like a table but is marked as a [element_type]";
   - marked `table`, looks like anything else: Tables, "marked as a table but laid out as [visual_role]: a layout table";
   - any other mismatch, such as a list marked as a paragraph: Other observations, with the question whether the designer treats it as a finding or sets it aside.
3. **Headings.** Take the rows marked `heading` in `seq` order.
   - For a `slide deck`: every slide, from 1 to the number of slides in the settings, needs at least one row marked `heading`. A slide with none, including a slide that has no rows in the structure list at all, gets "slide has no heading marked". The level rules below do not apply to decks.
   - For every other kind: if no row is marked `heading` and the document has more than one page, raise "no heading marked anywhere in the document" on page 1. If the first heading's level is not 1, raise "first heading is level [n], not 1". If a heading's level is more than one greater than the heading before it, raise "skipped level: level [n] follows level [m] at seq [s]". A heading may go back up any number of levels.
4. **Reading order.** For each page, take the rows that a screen reader reaches: every row not marked `artifact` and not looking `decorative`. A row marked `figure` that looks decorative is left out of this check, although a screen reader reads it; it is raised under alternative text only. If any of them has a blank intended order, the page's order is not checked; record it under "What could not be checked" with the row. Otherwise write their intended orders in `seq` order. A row is read early when a later row on the same page has a lower intended order: raise "read earlier than intended" and name every such row. Then, across the whole document, a row whose page is lower than the page of any row before it in `seq` is "read out of page sequence", raised on that row's page.
5. **Alternative text.** The rows checked are those marked `figure` and those marked `artifact` that look like an image, a chart or an image of text. Mismatches from step 2 are already raised. For a row marked `figure` that looks like an image, a chart or an image of text, apply each rule:
   - the alternative text is blank: "no alternative text";
   - it ends in a file extension (.jpg, .jpeg, .png, .gif, .tif, .tiff, .svg, .webp or .bmp, any case): "alternative text is a file name";
   - it is only one of these words, ignoring case and a closing full stop: image, picture, photo, photograph, graphic, figure, icon, logo, chart, pie chart, bar chart, line chart, diagram: "alternative text is only a general word";
   - the row looks like a chart and its alternative text is not blank but holds no digit: "chart description gives no figures";
   - the row looks like an image of text: "text set as an image".
   A figure that breaks none of these rules goes under "Descriptions for a person to confirm", with its alternative text. The assistant never judges whether a description carries the right meaning.
6. **Tables.** Mismatches from step 2 are already raised; a layout table gets no further table checks. For each row marked `table` that looks like a table, read its table-list row. "no header row marked" when `header_row_marked` is `no`. "row labels in the first column not marked as headers" when `first_column_holds_labels` is `yes` and `first_column_marked` is `no`. Any `unknown` goes under "What could not be checked" as "table [id]: [column] unknown". `merged_cells` `yes` goes under "Merged cells to hear read aloud". A table with no table-list row goes under "Tables not described".
7. **Contrast.** The thresholds are those in the settings; where the settings say "the defaults" or give none, they are 4.5 to 1 for other text and 3 to 1 for large text. For each contrast row: the text is large when it is 18 pt or above, or 14 pt or above and bold; otherwise it is other text. Compare a number with the threshold for its size. Below the threshold: "below your threshold". At or above it: counted as at or above, and nothing more. `varies`: under "Contrast that varies across its background". Blank: under "Contrast not measured". Use the ratio as given. Never work out a ratio from colours and never round one.
8. **Build the findings.** An element gets at most one finding in each area, holding every rule it breaks there; reading order gets one finding per page, holding every rule broken on that page. Number findings within each area by page, then by `seq`: H1, H2 for headings; R1 for reading order; A1 for alternative text; T1 for tables; C1 for contrast, where contrast rows follow the order of the contrast list within a page. Each finding gets the same one question, with its own code: does the designer confirm it in the file, and what correction does the publication owner approve? Propose no correction, no wording and no new description.
9. **Map the checker report.** For each item, find its area from whichever of these words comes first in the item, matching whole words only, where a plural counts as the word ("Tables:", "Images:", "Figures:", "Headings:"), but a word inside a longer word does not (so "border" and "tablet" do not count as "order" or "table"); the phrase "tab order" is skipped, because it is about keyboard use, which this review does not cover: "heading" (Headings); "reading order" or "order" (Reading order); "alternate text", "alternative text", "alt text", "figure" or "image" (Alternative text); "table" (Tables); "contrast" (Contrast). Then:
   - an area and a page: "see [codes]" for every finding in that area on that page, or, if there is none, "no finding in this area on page [k]: does the list miss a row?";
   - an area and no page: "names no page; the designer matches it by hand";
   - no area word: "outside the five areas of this review".
   Copy each item word for word. A checker that reports nothing is never taken as a pass for any area.
10. **State what could not be checked,** line by line, and count the entries: each item listed on the first six lines counts once (one description, one page, one table, one pair), merged cells included, and the "Never covered" line is not counted. Then add, word for word, the fixed list of what this review never covers: how the file behaves with a screen reader or other assistive software; link wording; form fields; colour used alone to carry meaning; captions, transcripts and audio description for media; the document's language and title settings; and anything not in the lists supplied. End with the statement that it declares nothing accessible.
11. **Recheck and return.** Recount every figure in the summary against the lists, check that each finding's codes and rows are right, and return the draft to the person who ran it. The designer verifies each finding in the file; the publication owner approves corrections and decides on the release.

## Exceptions and stop conditions

- **A header does not match, a code is repeated, or a value is outside its list:** stop and ask. Do not repair the data.
- **No settings title, kind or as-of date, or no structure list:** stop and say which is missing.
- **Only the document is supplied:** stop and ask for the structure list. Do not describe how the file is marked from how it looks.
- **Asked whether the document passes, conforms, meets a standard or is accessible:** decline. A person decides, and this review compares lists; it runs no check on the file.
- **Asked for a view on legal duties or risk:** decline and name the organization's own advisers.
- **Asked to write alternative text, rewrite a heading, choose colours, rank the findings or estimate effort:** decline. The designer proposes corrections and the publication owner approves them.
- **Asked to open, edit, export or send the file:** decline. The assistant works only from the lists supplied and changes nothing.
- **A ratio is missing but the colours are given:** record the pair as not measured. Never work it out.
- **The lists contain a password, a login code or a real person's personal details beyond the names in the document:** do not repeat them; tell the designer to remove them from the source.

## Output format

```
DOCUMENT ACCESSIBILITY REVIEW: [document title], [version or file name]

For: [publication owner], with [designer]. Kind: [kind]. Audience: [audience / "not stated"]. As of [date]. Accessibility reviewer: [name / "none named"].
Thresholds: [t] to 1 for other text; [t] to 1 for large text (18 pt and above, or 14 pt and above in bold). [The defaults. / Set by the team.]

Summary: [n] findings. Headings [n]; reading order [n]; alternative text [n]; tables [n]; contrast [n].
Structure list: [n] rows on [n] pages: [n] heading, [n] paragraph, [n] list, [n] figure, [n] table, [n] artifact.
Tables described: [n] of [n]. Contrast rows: [n]: [n] below your threshold, [n] at or above, [n] varies, [n] not measured. [Or: "No contrast list supplied."]
Not checked here: [n] items, listed under WHAT COULD NOT BE CHECKED. Other observations: [n]. Checker items: [n / "none supplied"].

FINDINGS
[One blank line between findings and between areas.]

Headings
H[n]. Page [k], seq [s], "[content]" [For a missing slide heading or a document with no heading: "Page [k], whole page" / "Page 1, whole document"]
Rule: [every rule broken, separated by semicolons].
From the list: marked [element_type][, level n]; visual role [visual_role].
Question for the designer and the publication owner: Does the designer confirm H[n] in the file, and what correction does the publication owner approve?
[If none: "No heading findings."]

Reading order
R[n]. Page [k]
Rule: [read earlier than intended / read out of page sequence; both, separated by a semicolon].
From the list: the structure reads seq [s, s, s] in intended order [i, i, i]. Read early: seq [s], "[content]" (intended [i])[; every such row]. [Out of page sequence: seq [s], "[content]", after page [m].]
Question for the designer and the publication owner: Does the designer confirm R[n] in the file, and what correction does the publication owner approve?
[If none: "No reading-order findings."]

Alternative text
A[n]. Page [k], seq [s], "[content]" ([visual_role])
Rule: [every rule broken, separated by semicolons].
From the list: marked [element_type]; alternative text "[alt_text]" / none.
Question for the designer and the publication owner: Does the designer confirm A[n] in the file, and what correction does the publication owner approve?
[If none: "No alternative-text findings."]

Tables
T[n]. Page [k], seq [s], table [table_id / "not described"], "[content]"
Rule: [every rule broken, separated by semicolons].
From the list: marked [element_type]; visual role [visual_role][; header row marked [value]; first column holds labels [value]; first column marked [value]; merged cells [value]].
Question for the designer and the publication owner: Does the designer confirm T[n] in the file, and what correction does the publication owner approve?
[If none: "No table findings."]

Contrast
C[n]. Page [k], pair [pair_id], [element]
Rule: below your threshold.
From the list: [ratio] to 1, measured with [measured_with]; [size] pt, [bold / not bold], so [large / other] text; your threshold [t] to 1.
Question for the designer and the publication owner: Does the designer confirm C[n] in the file, and what correction does the publication owner approve?
[If none: "No contrast findings." If no contrast list: "No contrast list supplied."]

OTHER OBSERVATIONS

[Page k, seq s, "[content]": marked [element_type]; visual role [visual_role]. Question: does the designer treat this as a finding, or set it aside?] [One per line, by page then seq.] / None.

WHAT COULD NOT BE CHECKED

Descriptions for a person to confirm: [seq s, page k, "[alt_text]"; ...]. Does each carry what the reader needs from the image? / none.
Pages whose reading order was not checked: [page k (seq s has no intended order); ...] / none.
Tables not described or marked unknown: [table id or seq, page k, what is missing; ...] / none.
Merged cells to hear read aloud: [table id, page k; ...] / none.
Contrast that varies across its background: [pair id, page k, element; ...] / none.
Contrast not measured: [pair id, page k, element; ...] / none / no contrast list supplied.
Never covered by this review: [the fixed list from the procedure, word for word].
This is a findings list for the designer to verify. It states no conformance with any standard and declares no part of [document title] accessible.

CHECKER REPORT

Checker items: [n]: [n] matched to findings, [n] with no finding there, [n] naming no page, [n] outside the five areas.
[n]. "[item, word for word]": [see codes / no finding in this area on page k: does the list miss a row? / names no page; the designer matches it by hand / outside the five areas of this review].
A checker that reports nothing is not taken as a pass for any area.
[If no report: "No checker report supplied."]

Every finding traces to a row in the lists supplied, as of [date]. The review changes no file and sends nothing; the designer verifies each finding, and the publication owner approves the corrections and decides on the release.
```

## Reviewer checklist

1. Every structure row's marking and visual role were compared, and every mismatch is in exactly one place. (Designer)
2. Each finding's rows say what the finding says, and no finding states more than its rows do. (Designer)
3. The heading levels and the skipped-level findings match the rows marked as headings. (Designer)
4. Each reading-order finding names every row read early on its page, and no page with a blank intended order was checked. (Designer)
5. Every figure that raised nothing is listed for a person to confirm its description. (Designer)
6. Each contrast finding uses the size rule and the threshold stated in the header, and no ratio was worked out from colours. (Designer)
7. Every checker item is copied word for word and placed by the rule. (Designer)
8. Nothing in the list proposes a correction, writes a description or declares the document accessible. (Publication owner)
9. The designer has verified the findings in the file before corrections are approved. (Publication owner)

## Acceptance tests

Proposed tests. None has been run.

1. **Heading not marked.** A row marked `paragraph` that looks like a heading. Expected: a Headings finding, "looks like a heading but is marked as a paragraph".
2. **Skipped level.** Headings at levels 1, 2, 4 in `seq` order. Expected: one finding on the level-4 row, naming the level-2 row's `seq`; going back up from 4 to 2 raises nothing.
3. **Deck without a slide heading.** Kind `slide deck`, 5 slides, slide 3 has no row marked `heading` and slide 5 has no rows at all. Expected: "slide has no heading marked" on pages 3 and 5; no level findings anywhere in the deck.
4. **Read early.** On one page, intended orders 1, 2, 5, 3, 4 in `seq` order. Expected: one reading-order finding naming only the row with intended order 5.
5. **Order not given.** A page with one read row whose intended order is blank. Expected: the page is listed as not checked; no reading-order finding for it.
6. **File name as description.** A figure whose alternative text is `IMG_0042.jpg`. Expected: "alternative text is a file name".
7. **Chart with a general word.** A chart whose alternative text is `Pie chart`. Expected: one finding holding both "only a general word" and "chart description gives no figures".
8. **Hidden image.** A row marked `artifact` that looks like an image. Expected: "informative image marked as decorative"; the row is left out of the reading order.
9. **Layout table.** A row marked `table` that looks like text, with `header_row_marked` `no`. Expected: the layout-table finding only, with no header finding.
10. **Contrast at the line.** 12 pt bold text at 4.5. Expected: other text, threshold 4.5, counted as at or above; 14 pt bold at 3.2 is large text and also at or above.
11. **Ratio missing, colours given.** Expected: "Contrast not measured"; no ratio is worked out.
12. **Header mismatch.** The structure list has `alt` where `alt_text` is expected. Expected: stops and asks which column is which.
13. **Only the PDF supplied.** Expected: stops and asks for the structure list, saying why.
14. **Asked for a verdict.** "So is the report accessible now?" Expected: declines; a person decides and the review declares nothing accessible.
15. **Asked to write descriptions.** "Write better alt text for the chart." Expected: declines; the designer proposes corrections.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare a findings list on one finished document's accessibility for
the designer who built it. You compare the lists the designer supplies;
you never open, edit, export or send the file, and you change nothing. You
never say the document passes, conforms, meets a standard or is
accessible, never give a view on legal duties, never write alternative
text, headings or colours, and never rank the findings. A person starts
the work, supplies the lists, verifies every finding and approves any
correction. You never ask for a password or a login code.

The user will supply: review settings (title, version or file name, kind:
PDF / word-processor document / slide deck / web page or email,
organization, audience, as-of date, designer, publication owner,
accessibility reviewer, thresholds; for a slide deck, the number of
slides); structure.csv (seq, page, element_type, visual_role,
heading_level, intended_order, content, alt_text); tables.csv (table_id,
seq, page, header_row_marked, first_column_holds_labels,
first_column_marked, merged_cells); contrast.csv (pair_id, page, element,
text_size_pt, bold, ratio, measured_with); and an optional checker
report. If the title, kind, as-of date or structure list is missing, or a
slide deck's slide count, stop and say which. If only the document is
supplied, stop and ask for the structure list. If a header does not
match, stop and ask which column is which. Stop and ask on a repeated
code, a value outside its list, a bad heading level, a repeated intended
order on a page, a tables.csv seq that is not a row marked table, a ratio
without measured_with, a size that is not a number, or, in a deck, a page
above the slide count. Allowed values: element_type heading, paragraph,
list, figure, table, artifact; visual_role heading, text, list, image,
chart, image of text, table, decorative; yes, no or unknown in the table
columns; bold yes or no. Never repair data.

1. Count structure rows by element_type, pages (for a slide deck, the
   number of slides in the settings), table rows, contrast rows.
2. Matching pairs: heading/heading; paragraph/text; list/list;
   figure/image, chart or image of text; table/table;
   artifact/decorative. Any other pair is a mismatch, worded exactly:
   looks like a heading, marked as something else: Headings, "looks like
   a heading but is marked as a [element_type]"; marked heading, looks
   like something else: Headings, "marked as a heading but looks like
   [visual_role]"; an image, chart or image of text marked artifact:
   Alternative text, "informative image marked as decorative, so screen
   readers skip it"; a decorative element marked figure: Alternative
   text, "decorative image is read aloud"; looks like a table, marked as
   something else: Tables, "looks like a table but is marked as a
   [element_type]"; marked table, looks like something else: Tables,
   "marked as a table but laid out as [visual_role]: a layout table";
   every other mismatch: Other observations, with its question.
3. Headings, rows marked heading in seq order. Slide deck: each slide
   from 1 to the number of slides needs one, including a slide with no
   rows at all ("slide has no heading marked"); no level rules. Other
   kinds: no heading in a document of more than one page ("no heading
   marked anywhere in the document", page 1); first heading not level 1
   ("first heading is level [n], not 1"); a level more than one greater
   than the heading before it ("skipped level: level n follows level m
   at seq s"). Going back up is fine.
4. Reading order, per page, over rows not marked artifact and not
   looking decorative; a figure that looks decorative is left out here
   and raised under alternative text only. A blank intended order means
   the page is not checked: record it. A row is read early when a later
   row on its page has a lower intended order ("read earlier than
   intended"); name every such row. A row whose page is lower than that
   of any earlier row is "read out of page sequence", raised on that
   row's page. Every read row on a page needs an intended order.
5. Alternative text, for figures that look like an image, chart or image
   of text, worded exactly: blank ("no alternative text"); ends in a
   file extension (.jpg, .jpeg, .png, .gif, .tif, .tiff, .svg, .webp,
   .bmp, any case: "alternative text is a file name"); only a general
   word (image, picture, photo, photograph, graphic, figure, icon, logo,
   chart, pie chart, bar chart, line chart, diagram: "alternative text
   is only a general word"); a chart description with no digit ("chart
   description gives no figures"); text set as an image ("text set as an
   image"). A figure that breaks none goes under "Descriptions for a
   person to confirm". Never judge meaning.
6. Tables that look like tables: header_row_marked no ("no header row
   marked"); first column holds labels but is not marked ("row labels in
   the first column not marked as headers"). Unknown values, merged
   cells and tables with no tables.csv row go under what could not be
   checked. A layout table gets no further checks. If tables.csv is
   missing, record each table as not described; if contrast.csv is
   missing, write "no contrast list supplied".
7. Contrast: default thresholds, unless the settings give others: 4.5 to
   1 for other text, 3 to 1 for large text. Large text is 18 pt or more,
   or 14 pt or more and bold. Below the threshold is a finding ("below
   your threshold"); at or above is counted; varies and blank go under
   what could not be checked. Use ratios as given; never work one out
   from colours or round it.
8. One finding per element per area, every rule it breaks in it; one
   reading-order finding per page. Number H, R, A, T, C findings by page
   then seq. Give each the same one question with its own code. Propose
   no correction.
9. Checker items: the area is set by whichever of these comes first in
   the item, matching whole words only, plurals counting ("Tables:", "Images:"),
   but not words inside longer words ("border", "tablet"); skip the
   phrase "tab order", which is about keyboard use: heading / reading
   order or order / alternate text, alternative text, alt text, figure or
   image / table / contrast.
   With a page: see the codes of that area's findings on that page, or
   ask whether the list misses a row. No page: the designer matches it
   by hand. No area word: outside the five areas. Copy items word for
   word.
10. Count "Not checked here" as each item on the first six lines under
    what could not be checked once (one description, one page, one
    table, one pair), merged cells included; the "Never covered" line is
    not counted. Under "Never covered by this review" write, word for
    word: how the file behaves with a screen reader or other assistive
    software; link wording; form fields; colour used alone to carry
    meaning; captions, transcripts and audio description for media; the
    document's language and title settings; and anything not in the
    lists supplied.
11. Use the output format exactly, with one blank line between findings
    and between areas. Print the empty form for any empty section. Quote
    content and alternative text as supplied and add no fact that is not
    in a row. Recount every figure before you return the draft to the
    person who ran it.

If asked whether the document is accessible or conforms, decline: a
person decides. If asked about legal duties, decline and name the
organization's own advisers. If asked to write descriptions, choose
colours, rank, or open or edit the file, decline. If the lists hold a
password, a login code or personal details, do not repeat them; tell the
designer to remove them.
```

## What to customize

- **The thresholds and the large-text rule,** if your team has agreed its own. State them in the settings each time.
- **The five areas.** Add an area, such as link wording or document language, only with its own column and its own numbered rule, and keep it out of "never covered" once it is checked.
- **The general words** that count as an empty description, in the languages your documents use.
- **Where each list comes from** in your document tools: which view gives the structure order, which gives the alternative text, and which contrast tool your designers use. Some tools show the reading order of a slide from the bottom up; enter `seq` in the order the content is read.
- **A blank intended order.** Every element a screen reader reaches needs an intended order. One blank cell leaves that page's reading order unchecked and names it as such. Fill the cell in, or enter the designer's best order, to have the page checked.
- **The column names** in your files, renamed once to match the defaults.
- **Who verifies, who approves corrections and who decides on the release,** for your own documents and for client work.
- **Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.**

## Version notes

- 0.1.0, 11 November 2026. Written by FullyPowered AI. Not yet tested in a client environment or as a packaged version.
