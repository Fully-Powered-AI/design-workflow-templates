# Trial: Current experience baseline, run on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

This is one run of the workflow template on its own invented example. The inputs are the invented ones in [the example](example.md) (Marlowe Example Store: the request, the nine-row page list and the seven described captures); no client data was used. The run was made by a model that had not written the template. It read the template and only the inputs of the example, followed the instructions block and the output format, and compared its result with the published example afterwards. The "captures" are written descriptions of screenshots, not image files, so this run did not test reading real images.

## What came out

The full output follows.

```
CURRENT EXPERIENCE BASELINE: Marlowe Example Store

Draft baseline, not confirmed. For Dana. Reason for the redesign, as supplied: replace the storefront theme before the spring launch. Captures dated 2026-10-12 to 2026-10-13.

1. WHAT WAS SUPPLIED
Pages listed: 9. Captures supplied: 7 (home-top.png, shop-full.png, product-jacket.png, cart.png, help-text.txt, about-full.png, account.png). Page limit: 40. Capture files named but not supplied: none. Files supplied but not in the list, set aside: none. The lead's notes, recorded as supplied and not as an observation from a capture: "the checkout header is reduced on purpose." Not measured: contrast, type sizes, load speed, accessibility compliance, how pages look on a phone.

2. COVERAGE BY SECTION
Home: 1 read, 0 outside the evidence.
Shop: 2 read, 0 outside the evidence.
Checkout: 1 read, 0 outside the evidence.
Help: 1 read, 1 outside the evidence.
Company: 1 read, 0 outside the evidence.
Account: 0 read, 1 outside the evidence.
Wholesale: 0 read, 1 outside the evidence.
Total: 6 read, 3 outside the evidence, of 9 listed. Sections with no evidence: Account, Wholesale.

3. PAGE RECORDS
P01 Home, /, section Home
Capture: home-top.png, screenshot-top, 2026-10-12. Top of the page only.
Purpose as shown: headline "Gear that outlasts the season"; main action "Shop all".
Content in order: header (logo text "Marlowe"; links "Shop", "Help", "About"; "Cart (0)"); hero with headline and the line "Free returns for 60 days"; three category cards "Jackets", "Packs", "Boots", each with a photo above its title; banner "New for autumn" (cut off by the end of the capture). Heading levels not recorded.
Content observations: the hero states "Free returns for 60 days". The three card titles are "Jackets", "Packs" and "Boots". The header cart label is "Cart (0)".
Design observations: as seen, a header with text logo and three links; a hero with one filled dark green button sized to its label; three cards in a row, photo above title; headings appear in a serif face, body text in a sans-serif face.
Not in this capture: everything below the "New for autumn" banner, including any footer; hover states; how the page looks on a phone.

P02 Shop all, /shop, section Shop
Capture: shop-full.png, screenshot-full, 2026-10-12.
Purpose as shown: headline "Shop all"; main action "Add to cart" (the button on each product card; no single page-level action is shown).
Content in order: header (same links, "Cart (0)"); heading "Shop all"; left column of filters "Category", "Size", "Price"; grid of 12 product cards; footer with three link columns (Shop: "Jackets", "Packs", "Boots"; Help: "Help centre", "Contact us"; Company: "About", "Careers", "Press"); box "Get 10% off your first order" with an email field and the button "Sign up"; the line "© 2022 Marlowe". Heading levels not recorded.
Content observations: 12 product cards, each with a photo, a name, a price and the button "Add to cart". Newsletter box reads "Get 10% off your first order". Footer line reads "© 2022 Marlowe".
Design observations: as seen, filters in a left column; cards in 3 columns and 4 rows; the card buttons are outlined green; heading in a serif face; footer in three link columns.
Not in this capture: hover states; how the filters open; how the page looks on a phone.

P03 Trail jacket, /shop/trail-jacket, section Shop
Capture: product-jacket.png, screenshot-full, 2026-10-12.
Purpose as shown: headline "Trail jacket"; main action "Add to bag".
Content in order: header (same, "Cart (0)"); breadcrumb "Shop / Jackets / Trail jacket"; gallery of 4 photos; name "Trail jacket"; price "$189"; size selector (XS, S, M, L, XL); button "Add to bag"; three tabs "Details", "Care", "Reviews (0)", with Details open; footer with the same three link columns; box "Join our list for 10% off your first order" with an email field and the button "Join"; the line "© 2022 Marlowe". Heading levels not recorded.
Content observations: price "$189". "Reviews (0)" shows no reviews. The action is labelled "Add to bag" while the header says "Cart (0)". Newsletter box reads "Join our list for 10% off your first order" with the button "Join". Footer line reads "© 2022 Marlowe".
Design observations: as seen, a gallery of 4 photos; one filled dark green button sized to its label; tabs with the first open; name in a serif face; footer in three link columns.
Not in this capture: the content of the Care and Reviews tabs; the size selector's behaviour; how the page looks on a phone.

P04 Cart, /cart, section Checkout
Capture: cart.png, screenshot-full, 2026-10-12.
Purpose as shown: headline "Your cart"; main action "Checkout".
Content in order: reduced header (logo text "Marlowe" and "Secure checkout"; no other links); heading "Your cart"; table with one line ("Trail jacket", size M, quantity 1, "$189"); "Subtotal $189"; button "Checkout"; one-line footer "Help centre | Contact us". Heading levels not recorded.
Content observations: one line item at "$189"; "Subtotal $189". No newsletter box and no copyright line are shown.
Design observations: as seen, a filled dark green button that runs the full width of the content area; header and footer reduced to a few words. The capture does not state the face of the heading.
Not in this capture: what the cart shows with more than one item; hover states; how the page looks on a phone.

P05 Help centre, /help, section Help
Capture: help-text.txt, saved text, 2026-10-13.
Purpose as shown: headline "Help centre"; main action not shown as a labelled action ("Search help" appears as text only).
Content in order: line "Marlowe / Shop / Help / About / Cart (0)"; heading "Help centre"; "Search help"; topics Orders, Shipping, Returns, Sizing, Payments, Contact us; under Returns, "Free returns for 30 days on unworn items."; link groups Shop (Jackets, Packs, Boots), Help (Help centre, Contact us), Company (About, Careers, Press); "Sign up for 10% off your first order / Sign up"; "© 2022 Marlowe". Heading levels not recorded.
Content observations: returns text reads "Free returns for 30 days on unworn items." Newsletter text reads "Sign up for 10% off your first order" with "Sign up". Footer line reads "© 2022 Marlowe".
Design observations: not observable from saved text.
Not in this capture: layout, colors, faces, imagery, buttons, spacing, hover states, how the page looks on a phone.

P06 About, /about, section Company
Capture: about-full.png, screenshot-full, 2026-10-13.
Purpose as shown: headline "About Marlowe"; main action: the capture shows none.
Content in order: header (same, "Cart (0)"); heading "About Marlowe" with one paragraph and a photo of a workshop; heading "Our story" with two paragraphs; heading "Our materials" with a bulleted list of three items; footer with the same three link columns; box "Get 10% off your first order" with a button "Sign up"; the line "© 2022 Marlowe". Heading levels not recorded.
Content observations: newsletter box reads "Get 10% off your first order" with "Sign up". Footer line reads "© 2022 Marlowe".
Design observations: as seen, one photo (a workshop); a bulleted list of three items; heading in a serif face; footer in three link columns.
Not in this capture: the text of the paragraphs and list items; hover states; how the page looks on a phone.

4. PATTERNS THAT RECUR
Header (named by assistant): seen on 6 of 6 read pages (P01, P02, P03, P04, P05, P06). Forms: full header (logo text, "Shop", "Help", "About", "Cart (0)") on P01, P02, P03, P06 and, as words only, P05; reduced header ("Marlowe" and "Secure checkout") on P04. Differences seen: "Secure checkout" and no links on P04 (the lead's note says this is on purpose). Not visible in this capture: none.
Footer (named by assistant): seen on 5 of 6 read pages (P02, P03, P04, P05, P06). Forms: three link columns Shop, Help and Company on P02, P03, P06 and, as words only, P05; reduced one-line "Help centre | Contact us" on P04. Differences seen: none beyond the reduced form. Not visible in this capture: P01 (top of page only).
Newsletter box (named by assistant): seen on 4 of 6 read pages (P02, P03, P05, P06). Forms: "Get 10% off your first order" with "Sign up" on P02 and P06; "Join our list for 10% off your first order" with "Join" on P03; "Sign up for 10% off your first order / Sign up" on P05. Differences seen: three wordings and two button labels, quoted above. Not visible in this capture: P01. P04 shows its footer without the box.
Copyright line (named by assistant): seen on 4 of 6 read pages (P02, P03, P05, P06). Forms: "© 2022 Marlowe" on all four. Differences seen: none seen. Not visible in this capture: P01. P04 shows its footer without it.
Filled dark green main button (named by assistant): seen on 3 of 6 read pages (P01, P03, P04). Forms: sized to its label on P01 ("Shop all") and P03 ("Add to bag"); full width of the content area on P04 ("Checkout"). Differences seen: width, as quoted. Not visible in this capture: P05 (saved text). P02 shows outlined green "Add to cart" buttons instead; P06 shows no button of this kind.
Heading face (named by assistant): a serif face seen on 4 of 6 read pages (P01, P02, P03, P06). Forms: serif headings on those four. Differences seen: none seen. Not visible in this capture: P05 (saved text); the P04 capture does not state it.

5. SEEN ONCE
Banner "New for autumn", P01. Three category cards with photos, P01. Left column of filters, P02. Grid of 12 product cards, P02. Breadcrumb, P03. Gallery of 4 photos, P03. Size selector, P03. Tabs, P03. Cart table, P04. "Search help" and help topics list, P05. Workshop photo and bulleted list of three items, P06.

6. WHERE PAGES SAY DIFFERENT THINGS
Returns period: "Free returns for 60 days" on P01; "Free returns for 30 days on unworn items." on P05.
Label for adding to the basket: "Add to cart" on P02; "Add to bag" on P03. The header on P01, P02, P03, P06 and the page on P04 use "Cart".
Newsletter wording and button: "Get 10% off your first order" / "Sign up" on P02 and P06; "Join our list for 10% off your first order" / "Join" on P03; "Sign up for 10% off your first order" / "Sign up" on P05.

7. OUTSIDE THE EVIDENCE
P07 Account: O3, the Access note says "Shows the signed-in customer's own orders"; account.png was supplied but is one person's view and was not read. To bring it in: the lead confirms it stays out.
P08 Wholesale portal: O1, Capture file blank; O3, the Access note says "Login required". To bring it in: a person with wholesale access takes a capture, or the lead confirms it stays out.
P09 Returns policy: O1, Capture file blank (the Access note is blank). To bring it in: a person captures the page, or the lead confirms it stays out.

8. VISIBLE NAMES WITH NO ROW IN THE PAGE LIST
Jackets: seen on P01 (card), P02, P03 (footer; breadcrumb on P03), P05, P06.
Packs: seen on P01, P02, P03, P05, P06.
Boots: seen on P01, P02, P03, P05, P06.
Contact us: seen on P02, P03, P04, P05, P06.
Careers: seen on P02, P03, P05, P06.
Press: seen on P02, P03, P05, P06.

9. QUESTIONS FOR THE LEAD
1. P07 Account shows one customer's own orders. Does it stay out of the baseline? The supplied account.png was not read.
2. P08 Wholesale portal needs a login and has no capture. Does it stay out, or will someone with access capture it?
3. P09 Returns policy has no capture and a blank Access note. Is it a public page, and can someone capture it? Pages P01 and P05 give different return periods.
4. The home capture stops at the "New for autumn" banner. Do you want the rest of the home page captured?
5. P05 is saved text, so its design cannot be observed. Do you want a screenshot of the help centre?
6. Jackets, Packs, Boots, Contact us, Careers and Press appear in navigation or footers but have no row. Should they be added to the page list?

10. THE LEAD'S CONFIRMATION
Baseline: [to be completed by the design lead.]
Changes to make: [to be completed by the design lead.]
Scope of the redesign: [to be written by the design lead.]
Confirmed by and on: [to be completed by the design lead.]

Every record traces to the capture it names, dated as shown, for Marlowe Example Store. The baseline visits no site, takes no capture, designs nothing and ranks nothing, and it sends nothing.
```

## What was observed

- **Every required part was produced.** All ten sections were present, in the order of the output format, and the counts agree: 6 read plus 3 outside the evidence equals the 9 pages listed, and the section totals match. Nothing in the template made the run stop: the headers matched, no ID or address was repeated, and the list was well under the page limit.
- **Same pages in and out as the example.** P01 to P06 were read. P07 (O3), P08 (O1 and O3) and P09 (O1) were outside the evidence. The extra supplied file, account.png, was not read.
- **Same differences found.** Return period (60 days against 30 days), "Add to cart" against "Add to bag", and the newsletter wording and button were all recorded with both versions quoted and no verdict. The six names with no row (Jackets, Packs, Boots, Contact us, Careers, Press) match the example.
- **Where this run differed from the published example.**
  - It listed two more recurring patterns, the copyright line and the heading face, and named the outlined card buttons on the shop page inside the main-button pattern. The example lists four patterns. The template does not say which elements count as a pattern, so both are defensible.
  - The example counts P05 (saved text) as showing the "full" footer with columns. This run called it "words only", because saved text has no layout.
  - It added a question about P09 (no capture and a blank access note) that the example does not ask. It asked the example's other questions in a different order.
  - Its confirmation block shows "[to be completed by the design lead.]" on the Baseline line; the example repeats the three choices there.
  - Its coverage notes are slightly longer per page (it spelled out the text of each block), and it did not put "6 topics" on P05.
- **Facts not in the inputs.** None found in either output. The phrase in the example's section 7 about capturing "a view that carries no real customer's data" is a suggestion, not a fact. This run's note that "Reviews (0)" "shows no reviews" is a reading of a label, not a separate fact.
- **Ambiguities where the run had to guess:**
  1. The output format's Baseline line reads "[confirmed, confirmed with changes or not confirmed; to be completed by the design lead.]", while step 11 says to leave the block empty. It is unclear whether to print the three choices or only a placeholder.
  2. The template does not say how many patterns to list or what counts as an element in a "recognizably the same role". The heading face, the copyright line and the main button are all arguable.
  3. It does not say how a saved-text page counts toward a pattern such as the header or footer whose words are present but whose layout is not. This run counted it and marked it "words only".
  4. "Main action" for a page with a button on every card (P02), with no button (P06) or with only a search label (P05) has no rule beyond "or say so".
  5. Step 9 lists names in navigation, footers and breadcrumbs, but the help page's topic list (Returns, Shipping) is neither. This run left the topics out. Whether "Returns" counts as matching the row "Returns policy" is not stated.
  6. For an O3 page, the template says what brings a page in ("a capture taken by a person with the right access") but that does not fit a personalized page. The example suggests a capture with no real customer's data; the template does not.
  7. The template does not say what to do with a blank Access note and a blank capture (P09). The run gave it O1 only and asked a question.
  8. The Access note wording is quoted in one place and paraphrased in another; the template does not say which.
- **Nothing was asked to stop for.** The run was not asked to design, rate, visit a site or send anything, so those refusals were not exercised. The acceptance tests in the template remain proposed; only the happy path was run here, and not the stop conditions.
- **Limits.** One run, one model, one product, on described captures. This shows the instructions can be followed to a complete and checkable output on the example. It does not show how the template performs on real screenshots or for a client.

## Changes made to the template after this run

After an independent review, the template and its example were edited. The run above was not repeated, and nothing above was altered. The edits follow what this run did or settle ambiguities it raised: the Baseline line now prints only a placeholder (ambiguity 1); a saved text page is counted by its words and its form recorded as "words only" (ambiguity 3); a page with no single main action is stated as such (ambiguity 4); rows of category cards count for names with no row and topic lists inside a page do not (ambiguity 5); a personalized page may be brought in by a capture of a view with no real person's data (ambiguity 6); and the Access note is quoted (ambiguity 8). The example was corrected to agree: P05 is "words only" in the header and footer patterns and "not visible" for the main action button, and the Baseline line shows the placeholder. Ambiguities 2 and 7 were not settled by those edits.

A second review then asked for further changes, and they were made without repeating the run. The example was corrected where it stated more than its inputs show (the newsletter box on the about page has a button and no email field shown; "Search help" on the help page is words, not a box) and where it gave a single main action for a page with an action on every card. The template now says that a shared visual property such as the heading face is a design observation and a single line such as the copyright line belongs in its element's forms, neither being a pattern of its own (settling ambiguity 2 in part: this run listed six patterns, the example four). The instruction block now also carries the labelling of the lead's notes, the "supplied and not read" rule for analytics reports, the rule for words addressed to an AI reader, and the draft marking; the output format's wording for the lead's notes and for set-aside files was aligned, and a supplied capture of a personalized page now always raises a question. The inputs and the output format's sections are unchanged. A third review then asked for small edits, made without repeating the run: the example's section 1 labels now match the output format, the example quotes its pattern differences and the header link exactly ("Cart (0)"), P05's "Content in order" gains its heading "Help centre", and the template states the default page limit of 40 in the instruction block, that a blank Access note with a blank capture is O1 only (the open point in ambiguity 7 above, which stays recorded as it was) and that a phrase such as "Secure checkout" is not a visible name. The edited instruction block has still not been run again, so the published wording is untried and this record covers the earlier wording; a rerun would differ on patterns, the notes line and the set-aside line.
