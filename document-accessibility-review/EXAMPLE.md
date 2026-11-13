# Document accessibility review: an invented example

*Illustrative example with invented data.* Client K is an invented regional arts charity and Studio M an invented design studio. The annual review, its pages, the funders named only by letter, the tools named only by letter, the roles and every row below are invented. The designer at Studio M listed how the finished PDF is built and what each element looks like, measured contrast and pasted the checker's items. The assistant compared the lists and returned the findings list. Nothing here describes a real document or a real review.

## The inputs

### 1. Review settings

```
Document: Annual review 2026
File: annual-review-2026-v3.pdf
Kind: PDF
Organization: Client K (an invented regional arts charity)
Audience: members, funders and the public
As-of date: 2026-11-10
Designer: the designer at Studio M
Publication owner: Client K's head of communications
Accessibility reviewer: none
Thresholds: the defaults
```

### 2. Structure list (structure.csv)

```
seq,page,element_type,visual_role,heading_level,intended_order,content,alt_text
1,1,heading,heading,1,1,Annual review 2026,
2,1,artifact,decorative,,,Background wave pattern,
3,1,figure,image,,2,Cover photo of a summer workshop,IMG_0042.jpg
4,1,paragraph,text,,,A year of open studios,
5,2,heading,heading,2,1,Welcome from the chair,
6,2,paragraph,text,,2,This year the studios opened on more weekends,
7,2,figure,image,,3,Portrait of the chair,The chair standing in the main gallery
8,2,paragraph,heading,,4,Where the money came from,
9,2,figure,chart,,5,Pie chart of income by source,Pie chart
10,3,heading,heading,4,1,Programmes,
11,3,paragraph,text,,2,Open studios ran every Saturday,
12,3,paragraph,text,,5,Pull quote: I found my people here,
13,3,table,table,,3,Attendance by programme,
14,3,paragraph,text,,4,Figures include repeat visits,
15,3,artifact,image,,,Photo of children painting a mural,
16,4,heading,heading,2,1,Thank you,
17,4,paragraph,list,,2,Our funders: Funder A; Funder B; Funder C,
18,4,figure,decorative,,,Decorative swirl,decorative swirl
19,4,figure,image of text,,3,Contact box with address and phone number,Contact us
20,4,table,text,,4,Footer in two columns: address and charity number,
```

### 3. Table list (tables.csv)

```
table_id,seq,page,header_row_marked,first_column_holds_labels,first_column_marked,merged_cells
TB1,13,3,yes,yes,no,yes
TB2,20,4,no,no,no,no
```

### 4. Contrast list (contrast.csv)

```
pair_id,page,element,text_size_pt,bold,ratio,measured_with
K1,1,Title over the cover photo,36,yes,varies,Contrast tool A
K2,1,Subtitle on the cover,14,no,3.9,Contrast tool A
K3,2,Body text,10,no,8.2,Contrast tool A
K4,2,Chart labels,12,yes,4.5,Contrast tool A
K5,3,Pull quote,20,no,3.4,Contrast tool A
K6,3,Table text on shaded rows,9,no,4.4,Contrast tool A
K7,4,Charity number in the footer,8,no,,
```

### 5. Checker report (pasted)

```
Alternate text: page 1, figure alternate text may be a file name
Headings: page 2, text styled as a heading is not tagged as one
Primary language: not set
Reading order: needs manual check
```

## The findings list

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

## What happens next

The designer opens the PDF and confirms each finding, listens to the attendance table with its merged cells, checks the title over the cover photo by eye and measures the charity number. Client K's head of communications approves the corrections. The designer makes them and runs the review again on the next version with fresh lists.
