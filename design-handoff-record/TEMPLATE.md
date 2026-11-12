# Design handoff record

Workflow template, version 0.1.0.

## Purpose

Turn one approved design into a handoff record for engineering: for every item in the design, which states it needs and where each is shown or documented; the tokens it uses with their values; the layout shown at each breakpoint; the rule for each piece of content; and what each control does. Every behaviour the design does not state is written as a numbered question for the design owner. The assistant records and asks. It creates no design, never fills a gap with a sensible default, never copies behaviour from a similar component, and never marks a question answered.

## When to use it and when not to

Use it when an approved design is ready for engineering and before the engineer estimates or builds. Run it again with corrected files if the design changes.

Do not use it:

- to create or improve a design, or to say what an unstated state should look like. The design owner does that;
- to turn a story into testable expectations. Acceptance criteria sheet does that, and can start from the answered record;
- to check a finished project before a receiving team takes it on. Project handover readiness check does that;
- to document one component in full for the design library, with its variants, usage rules and accessibility notes. Component specification does that;
- to review the design's quality, accessibility or fit for users, or to check that a build matches the design.

## Roles

- **Runs it:** the design owner, or the designer who prepared the design.
- **Answers the questions and approves the record:** the design owner named in the settings.
- **Confirms that every question is resolved:** the engineer named in the settings.
- **Changes the design, the design library or the build afterwards:** people the company names. Never the assistant.

## Inputs

All are pasted or attached by a person, as plain text or CSV. Nothing is connected to a design tool, a code repository or a ticket system. Column headers are matched by name, ignoring case and column order. Extra columns are ignored and named in the header of the record. If a header listed below is missing or renamed, stop: name the file, the header expected and the headers found, and ask the person to correct the file or say which column holds it. Never guess a column. If the design exists only as images, the person writes the inventory first; the assistant reads only what is written.

1. **Design inventory.** Headers `item_id`, `screen`, `width`, `component`, `kind`, `state`, `content`, `tokens`, `description`. One row per component, in one state, at one width.
   - `item_id` is one component on one screen, repeated on each of its rows (D1, D2 and so on).
   - `width` is a whole number of pixels.
   - `kind` is one of Static, Control, Field or Data. A Control is something a person acts on, such as a button or link. A Field takes typed or chosen input. Data shows content that is loaded or entered, such as a list or table. Static is everything else.
   - `state` is one of default, hover, focus, pressed, disabled, loading, empty or error.
   - `content` and `tokens` may hold several names separated by semicolons, and may be blank.
   - `description` is a short plain statement of what the design shows. It may be blank.

   If there are no rows, stop and ask.
2. **Component references.** Headers `component`, `states_documented`, `reference`. One row per component in the design library, with its documented states separated by semicolons. Optional. If missing, write "no component references supplied" and treat every state not shown in the design as unstated.
3. **Tokens.** Headers `token`, `value`, `used_for`. Optional. If missing, write "no token list supplied" and ask a question for each token name used.
4. **Content rules.** Headers `rule_id`, `applies_to`, `max_length`, `overflow`, `format`. `applies_to` is the name of a content field. `max_length` and `format` may be blank. Optional. If missing, write "no content rules supplied" and ask a question for each content field.
5. **Interaction decisions.** Headers `decision_id`, `item_id`, `trigger`, `result`. Optional. If missing, write "no interaction decisions supplied".
6. **Settings.** The product, the design name and version, the smallest supported width in pixels, the breakpoints (a name and a starting width for each), the design owner, the engineer and today's date. If the smallest supported width, the breakpoints, the design owner or the engineer is missing, stop and ask. If today's date is missing, write "today not given".

The assistant works only from what is supplied. It never asks for a password or a login code, and it does not repeat personal details that appear in the files.

## The procedure

1. **Check the inputs.** Confirm every header. Stop and ask if a `kind` or `state` is not in its list, a `width` is not a whole number, two rows share an `item_id`, `state` and `width`, rows with one `item_id` disagree on screen, component or kind, two component references share a component name, two content rules share an `applies_to`, or two decisions share a `decision_id`.
2. **Group the rows.** Rows with the same `item_id` form one item. Items and screens keep the order in which they first appear.
3. **Set aside narrow rows.** A row whose width is below the smallest supported width goes under Set aside, with the width and the supported minimum, and takes no part in later steps. If every row of an item is set aside, the item is listed only under Set aside.
4. **List the required states.** The set depends on the kind:
   - Static: default.
   - Control: default, hover, focus, pressed, disabled, loading.
   - Field: default, hover, focus, disabled, error.
   - Data: default, loading, empty, error.

   A state outside the set that the design shows is listed as "Also shown". It is never a gap.
5. **Cover each state.** For each required state, in the order above:
   - If a row of the item has that state, it is shown. List the widths in the order they first appear and quote each row's description, if any.
   - Otherwise, if the item's component has a reference row (matched by name, ignoring case) that lists the state, it is documented by the component library only. Cite the reference.
   - Otherwise it is unstated: ask a question. A component with no reference row is noted as "none supplied".

   Never infer a state from a similar component, a neighbouring screen or common practice.
6. **Check the tokens.** Collect the distinct token names across an item's rows, in order of first appearance. A name found in the token list is printed with its value. A name not found gets a question. If an item names no token on any row, ask whether it uses library values or one-off values.
7. **Work out the breakpoint ranges.** Sort the breakpoints by starting width. The first range starts at the smallest supported width; each range ends one pixel before the next breakpoint starts; the last has no end. For each screen and each range, the layout is shown if any retained row of that screen has a width in the range: list the items and widths. Otherwise ask a question naming the range. Coverage is checked per screen, not per item: an item with no row in a range is not flagged, and the design owner should know this. Never describe how a layout would behave between two designs.
8. **Check the content.** Collect the distinct content fields across an item's rows, ignoring case, and list each field once with the items that show it. Match each field to a content rule by `applies_to`, ignoring case.
   - No rule: one question asking for the longest value that can occur and what happens when a value is longer than the design shows.
   - A rule with a blank `max_length`: a question asking for the longest value.
   - A rule with a blank `overflow`: a question asking what happens when a value is longer than the design shows.
   - A blank `format` is printed as "no format stated" and raises no question.

   A rule whose `applies_to` matches no content field in the retained rows goes under Set aside.
9. **Check the interactions.** For each item, list its interaction decisions as written. For each Control and Field with none, ask what happens when the person uses it. A decision that names an `item_id` not in the inventory goes under Set aside with the question of which item is meant.
10. **Number the questions.** Number them Q1, Q2 and so on in the order they appear in the record: items and their states and tokens, then responsive behaviour, content rules and interactions. Each question carries its number in the place it arises. Every question starts as Open and names the design owner as the person who answers. Questions are never combined across items.
11. **Count.** Count required states covered and unstated, questions, and set-aside lines. Required states covered plus unstated must equal the required states of all retained items.
12. **Return the record** to the design owner. The design owner answers the questions and approves; the engineer confirms they are resolved. A person changes the design, the library or the build afterwards.

## Exceptions and stop conditions

- **A header does not match, a value is not in its list, a repeat is found, or there are no inventory rows, no breakpoints, no design owner or no engineer:** stop and ask.
- **Asked to fill a gap, suggest a likely answer, copy behaviour from another component or say what the engineer should assume:** decline and name the design owner.
- **Asked to say whether a state is needed (for example, whether a button can really fail):** decline. The question stays for the design owner, who may answer that it does not apply.
- **Asked to check the design for quality or accessibility, to compare the build with the design, or to write tickets or tests:** decline. The record only lists what the design states and leaves open.
- **Asked to send the record, update the design library or mark a question answered:** decline. Nothing is sent or changed.
- **A file contains passwords, login codes or other personal details:** do not repeat them; tell the person to remove them.

## Output format

```
DESIGN HANDOFF RECORD: [product], [design name and version]

For: the [design owner role] and the [engineer role]. Prepared: [date / today not given], from [n] inventory rows, [n component references / no component references supplied], [n tokens / no token list supplied], [n content rules / no content rules supplied], [n interaction decisions / no interaction decisions supplied] and the settings. [Extra columns ignored: ...]
Column check: all headers matched.
Items: [n] on [n] screen(s). Required states: [n] covered, [n] unstated. Questions: [n]. Set aside: [n].

ITEMS

[screen]
[item_id] [component] ([kind]); component reference: [reference / none supplied].
  [state]: [shown at [width], "[description]"; shown at [width], "[description]" / component library only ([reference]) / Q[n]]
  [one line for each required state, in order]
  Also shown: [states / none].
  Tokens: [token = value; token = value; token: Q[n]].
[None. if empty]

RESPONSIVE BEHAVIOUR

Breakpoints: [name from [px] to [px]; ...; name from [px]]. Smallest supported width: [px].
[screen], [name] ([from] to [to] px; for the last range, [from] px and over): [items at widths / Q[n]]
[None. if empty]

CONTENT RULES

[field] (on [item ids]): rule [rule_id]: longest [max_length / Q[n]]; when longer [overflow / Q[n]]; format [format / no format stated].
[field] (on [item ids]): no content rule. Q[n].
[None. if empty]

INTERACTIONS

[item_id] [component]: [decision_id]: [trigger] -> [result]. [Q[n] where a Control or Field has none.]
[None. if empty]

QUESTIONS FOR THE DESIGN OWNER

Q[n] [item_id and component / screen / field]: [the question, in the fixed wording].
  Status: Open. Answer: ______ Answered by: ______ Date: ______
[None. if empty]

SET ASIDE

[row, rule or decision]: [reason]. [The question for the person.]
[None. if empty]

SIGN-OFF

Design owner: has answered every question and approves this record: ______ Date: ______
Engineer: confirms all [n] questions are resolved and every set-aside line is dealt with: ______ Date: ______

Draft for the [design owner role]. No design has been created or changed, no behaviour has been assumed, and nothing has been sent.
```

Notes on the format:

- Count the inventory rows supplied, including any set aside. Print `screen(s)` literally.
- In Responsive behaviour, list each width once, in the order widths first appear, followed by the item ids shown at it, for example "D1, D3 at 390; D4 at 500".
- In Interactions, give a line only to an item that has a decision or a question. A Static or Data item with no decision gets no line.
- A breakpoint question is labelled with the screen and the range name, a content question with the field, and every other question with the item id and component.
- Set aside lines go in this order: inventory rows, content rules, interaction decisions.

The fixed wording of the questions is below. Use these words and no others.

- A state: "No [state] state is shown in the design or documented for [component]. What does it look like, and when does it appear?"
- A token: "The token [token] is named for [item_id] but is not in the token list. Which token or value is meant?" With no token list: "The token [token] is named for [item_id] and no token list was supplied. What is its value?"
- An item with no token: "No token is named for [item_id]. Does it use library values or one-off values, and which?"
- A breakpoint: "The design shows no layout for [screen] between [from] and [to] px. What should the screen do there?" For the last range: "at [from] px and over".
- A field with no rule: "No content rule exists for [field]. What is the longest value that can occur, and what happens when a value is longer than the design shows?"
- A blank length: "Content rule [rule_id] gives no longest value for [field]. What is the longest value that can occur?"
- A blank overflow: "Content rule [rule_id] gives no behaviour for [field] when a value is longer than the design shows. What happens?"
- An interaction: "No interaction decision is supplied for [item_id]. What happens when the person uses it?"
- A narrow row, after the reason "the width is below the smallest supported width of [px], so the row takes no part": "Is [width] to be supported? If so, the smallest supported width in the settings changes and the record is run again."
- An unknown item, after the reason "it names [item_id], which is not in the design inventory": "Which item is meant?"
- A content rule matching no field has the reason "it applies to [field], which no retained row shows", and no question.

## Reviewer checklist

1. Every description quoted is word for word from the inventory row with the same item, state and width. (Design owner)
2. Every required state of every item is listed once, as shown, documented or a question, and the counts add up. (Design owner)
3. No state, token, layout or behaviour appears that is not in the inputs. (Design owner)
4. Every token value matches the token list, and every token missing from the list has a question. (Design owner)
5. Every breakpoint range is correct and each range without a retained row has a question. (Design owner)
6. Every content field appears once and every blank or missing rule has its question. (Design owner)
7. Every Control and Field has a decision or a question. (Engineer)
8. Questions are numbered in the order they appear, use the fixed wording and suggest no answer. (Engineer)
9. Nothing has been sent, answered on anyone's behalf or changed. (Design owner)

## Acceptance tests

Proposed tests. None has been run.

1. **Documented but not shown.** A Control whose component documents loading, with no loading row. Expected: loading is listed as component library only, with the reference, and no question.
2. **Not shown and not documented.** A Field with no disabled row and no disabled in its component's list. Expected: the state question for disabled.
3. **Unknown token.** An item names space.5, absent from the token list. Expected: a token question, and the other tokens printed with their values.
4. **Missing breakpoint.** Breakpoints at 360, 768 and 1200, a screen with rows at 390 and 1280 only. Expected: the 768 to 1199 range gets a question; the ranges for 360 to 767 and 1200 and over list their items and widths.
5. **Row below the minimum.** A row at 320 with a smallest supported width of 360. Expected: set aside, not used for coverage.
6. **Blank length.** A rule with a blank `max_length` and a filled `overflow`. Expected: only the length question; the overflow is printed.
7. **Field with no rule.** Expected: one question using the fixed wording, listing every item that shows the field.
8. **Header mismatch.** The inventory has `status` instead of `state`. Expected: stops, names the file, the header expected and the headers found.
9. **Asked to suggest an answer.** Expected: declines, names the design owner, leaves the question open.
10. **Empty optional file.** No interaction decisions. Expected: every Control and Field raises the interaction question and the header says none was supplied.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format and the fixed question wording above.

```
You prepare a design handoff record for the design owner and the engineer.
You create no design, assume no behaviour, and never answer a question for
anyone. You never send the record or change a design, a library or a build.
A person approves everything that follows from it.

The user will supply: the design inventory (item_id, screen, width,
component, kind, state, content, tokens, description), component references
(component, states_documented, reference), tokens (token, value, used_for),
content rules (rule_id, applies_to, max_length, overflow, format),
interaction decisions (decision_id, item_id, trigger, result), and settings:
product, design name and version, smallest supported width, breakpoints
(name and starting width), design owner, engineer, today's date. Match
headers by name, ignoring case and order; extra columns are ignored and
named in the header of the record. If a header is missing or renamed,
or the inventory, breakpoints, design owner or engineer is missing, stop and
ask: name the file, the header expected and the headers found. Never guess a
column. Never ask for a password or a login code.

1. Check: kind is Static, Control, Field or Data; state is default, hover,
   focus, pressed, disabled, loading, empty or error; width is a whole
   number; no repeated item, state and width; rows with one item_id agree on
   screen, component and kind; no repeated component reference (by name);
   no two content rules sharing an applies_to; no repeated decision_id. Stop
   and ask on any failure. A missing optional file is named in the header
   ("no token list supplied" and so on) and treated as empty: with no
   component references every state not shown is unstated; with no token list
   ask for each token name; with no content rules ask for each field. A
   missing date prints "today not given".
2. Group rows by item_id, keeping order of first appearance. Rows below the
   smallest supported width go under Set aside and take no further part. An
   item whose rows are all set aside appears only under Set aside.
3. Required states: Static, default. Control, default, hover, focus, pressed,
   disabled, loading. Field, default, hover, focus, disabled, error. Data,
   default, loading, empty, error. Other states shown are "Also shown".
4. For each required state, in the order of step 3: shown (list widths in order of first appearance and quote descriptions); else
   component library only (cite the reference, matched by component name);
   else a question. A component with no reference row is noted as "none
   supplied". Infer nothing from similar components or common practice.
5. Tokens: print each distinct token with its value from the list; a token
   not in the list gets a question; an item naming no token gets a question.
6. Breakpoint ranges: sort by starting width; the first starts at the smallest
   supported width, each ends one pixel before the next, the last is open.
   For each screen and range, list the items and widths shown, or ask.
   Coverage is per screen: an item with no row in a range is not flagged.
7. Content: list each distinct field once (ignoring case) with its items.
   Match a rule by applies_to, ignoring case. Ask for a missing rule, a
   blank max_length and a blank overflow. A blank format prints as "no format stated". A rule matching no
   field goes under Set aside.
8. Interactions: list decisions as written. Ask for each Control and Field
   with none. A decision naming an unknown item goes under Set aside.
9. Number questions Q1, Q2 in the order they appear in the record. Use the
   fixed question wording, including the two set-aside questions, and no
   other words, and suggest no answer. Check that covered plus unstated
   states equals all required states, then count.
10. Use the output format exactly. In the header, count the inventory rows
   supplied, print screen(s) literally, and name any extra columns ignored.
   In Responsive behaviour list each width once, in order of first
   appearance, with its item ids (D1, D3 at 390). In Interactions give a line
   only to an item with a decision or a question. Label a breakpoint question
   with the screen and range, a content question with the field, any other
   question with the item id and component. Set aside lines go in this order:
   rows, rules, decisions. Print None. for an empty section. End with:
   "Draft for the [design owner role]. No design has been created or
   changed, no behaviour has been assumed, and nothing has been sent."

If asked to fill a gap, suggest an answer, say whether a state is needed,
review the design or the build, or mark a question answered, decline and
name the design owner.
```

## What to customize

- The column headers of your design inventory, and who exports it from your design tool.
- Your breakpoints and your smallest supported width.
- The states required for each of the four kinds, if your design library uses others.
- The kinds themselves, if you split Data into more.
- The fixed wording of the questions, to match how your team writes them.
- Who is the design owner for each product, who answers when they are away, and where the answered record is kept.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Tried on its invented example in Claude on 10 November 2026, run twice, the published record being the second and not blind (the record is published with it); not yet tested in a client environment. Minor edits after review: instruction block made self-contained, format and set-aside wording fixed, and the sibling Component specification named.
