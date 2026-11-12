# Component inventory audit

Workflow template, version 0.1.0.

## Purpose

Turn one design-library export, its documentation and its current token definitions into one inventory for the design-system owner: every component with its category, status, variants, documented states and tokens; a numbered list of naming, token, state and documentation gaps; notes on the token file itself; and the pairs of components that may overlap, with the signals that suggested it and a blank for the owner's decision. The assistant prepares; it changes no library, proposes no design, judges no appearance, and never merges, renames or retires anything. A possible overlap is a question for the owner, never a conclusion.

## When to use it and when not to

Use it when a library's patterns come up for review: on a schedule, before a cleanup, when two libraries are being compared or when a team asks why there are two of something. Run it again after fixes to see what is still open.

Do not use it:

- to design, redesign or name a new component, or to say which of two components looks better;
- to check accessibility, contrast or visual quality, which need people and tools looking at the real interface;
- to write component documentation. It reports where documentation is missing; the owners write it;
- to check a spreadsheet before it is shared (spreadsheet check before sharing) or to describe what a data export contains (dataset profile);
- when the export is not text. Images, screenshots and design files are not read; if any are supplied, say so and ignore them.

## Roles

- **Runs it:** the design-system owner, or a design operations lead working for them.
- **Decides every consolidation, retention and investigation, and approves any change to the library:** the design-system owner.
- **Answers questions about a component:** the owner named for it in the export, usually a designer or frontend engineer.
- **Makes any change to the library or its documentation:** the people who maintain them, after the owner's decision.

## Inputs

1. **Audit settings,** as a list of `name: value` lines. Required: `Library`, `Design-system owner`, `Operator` and `Export date` (YYYY-MM-DD). Optional: `As-of date`; `Component naming rule` (`pascal`, `kebab`, `title` or `as listed`; default `pascal`); `Token naming rule` (default: lowercase letters, digits and hyphens, in at least two groups separated by dots, such as `color.text-primary`); `Required states` (items separated by semicolons; default `default; hover; focus; disabled`); `Required states for <category>` (one line per category that needs a different list); `Qualifier words` (default: old, new, legacy, copy, temp, final, alt, any `v` followed by digits, and a bare number); `Deprecated status word` (default `deprecated`). If a required setting is missing, stop and ask.
2. **Components** (components.csv), one row per component, with these headers: `component_id`, `name`, `category`, `status`, `purpose`, `variants`, `states`, `states_not_applicable`, `tokens_used`, `docs_ref`, `owner`. `variants`, `states`, `states_not_applicable` and `tokens_used` hold items separated by semicolons. `docs_ref` is a reference or address to the documentation, or `none`. The assistant reads what is supplied and never opens an address. If the file is missing, stop. If a header does not match, stop and ask which column is which; never guess.
3. **Token definitions** (tokens.csv), with these headers: `token_name`, `value`, `type`, `status`. If the file is missing, say "token definitions not supplied", skip the checks that need it and run the rest. If a header does not match, stop and ask.

Appearance is not an input. The assistant works only from the text supplied, needs no connection to a design tool or code repository, and never asks for a password, a login code or a key; if one is pasted in, it does not copy it and tells the person to remove it.

## The procedure

1. **Check the inputs.** Confirm one library. Stop if `component_id` repeats or the file has no rows. Trim spaces on every item and compare items by exact text, ignoring case, except that token names are always matched with case, and except where a step says otherwise. A blank cell is treated as nothing supplied, never as a guess.
2. **Split each name into words.** Split on spaces, hyphens, underscores and dots, and where a lower-case letter is followed by an upper-case one. A letter-and-digit word such as `V2` stays whole. Write the words in lower case. The **name key** is the words joined together. Remove every qualifier word to get the **base name**; if nothing is left, the base name is empty and no signal uses it.
3. **Naming checks,** one gap each per component:
   - **Rule.** `pascal` means words joined with each starting in upper case and only letters and digits; `kebab` means lower-case words with single hyphens; `title` means capitalised words with single spaces; `as listed` skips this check. A name that breaks the rule is a gap, and the gap says how. A blank name is a gap.
   - **Same name.** If two components have the same name key, each is a gap that names the other.
   - **Qualifier.** If a name contains a qualifier word, it is a gap that gives the word.
4. **Token checks,** over `tokens_used`, one gap each per component, listing every item affected:
   - **None listed.** A blank `tokens_used` is a gap.
   - **Raw value.** An item that begins with `#` or a digit, begins with `rgb(`, `rgba(` or `hsl(`, or ends in `px`, `rem`, `em`, `ms` or `%` is a raw value, not a token name. It is a gap. A raw value is classed only as raw: it is never also checked as not defined or deprecated.
   - **Not defined.** A token name that is not in the token file is a gap. Token names are matched with case: a name that differs from a defined name only in case is not defined, and the gap says so. Skip this check if the token file was not supplied.
   - **Deprecated.** A token whose status is the deprecated word is a gap.
5. **State check,** one gap per component. The required states are the setting for the component's category, or the general list. A required state is met when it is in `states`, or in `states_not_applicable`. A blank `states` is one gap that says no states are documented. Otherwise one gap lists every required state that is neither documented nor marked not applicable. A state documented beyond the required list is shown in the inventory and is not a gap.
6. **Documentation checks,** one gap each per component: a blank or `none` `docs_ref`, and a blank `purpose`.
7. **Number the gaps** in the order of the export, and within a component in this order: naming, tokens, states, documentation. Within the token gaps, a blank `tokens_used` stands alone; otherwise order the gaps by the first item each one affects in `tokens_used`, and where two start at the same item, in the order of the checks in step 4. For each give the component, the kind, what is wrong, what would resolve it and who can supply it: the component's `owner`, or `not stated`.
8. **Token notes,** from the token file, each printed as `none` when empty:
   - **(a)** names that break the token naming rule;
   - **(b)** defined tokens used by no component in this export. If the person says the export is partial, add that this list may be longer than the truth;
   - **(c)** tokens with the same value and the same type under different names, by exact value ignoring case. Say that this may be one decision or two, and that the export cannot show which.
   These are observations. They are not gaps and carry no numbers.
9. **Possible overlaps.** Compare every pair of components in the export. Three signals exist: **A** the two base names are the same; **B** the two `tokens_used` lists hold the same items, in any order, and are not blank; **C** the two `variants` lists hold the same items, in any order, and are not blank. A pair is a possible overlap when at least two signals match. No other test is applied: not purpose wording, not category, not status. A naming gap on a component (such as a qualifier word) is reported in the gaps only and is not repeated as a reason on the pair. For each pair, print the signals matched, each component's purpose as supplied, and the differences the export does show: variants and documented states found in one and not the other, and any difference in category or status. Leave the owner's decision blank. Number the pairs in the order of their first component, then second.
10. **Summarise.** List categories and statuses in alphabetical order. Count components, categories, statuses, components with no gaps, gaps by kind, token references (each distinct item per component) as defined and not deprecated, deprecated, not defined and raw values, token definitions and possible overlaps. The four reference counts must add up to the total; if they do not, recount before returning.
11. **Close.** State that no library has been changed and no design proposed. End with the trace line and return the inventory to the person who ran it only.

## Exceptions and stop conditions

- **A required setting is missing:** stop and ask.
- **A header does not match the default:** stop and ask which column is which.
- **`component_id` repeats, or there are no components:** stop and report which.
- **The token file is missing:** say so, skip the not-defined and deprecated checks and token notes, and continue.
- **Two components look the same by name or purpose but fewer than two signals match:** list neither as an overlap. Different names can mark different uses.
- **Asked to merge, rename, retire or recommend which to keep, to say a component should be removed, to judge how something looks, to design a replacement or to change the library or its documentation:** decline; the owner decides.
- **Asked to open an address or read an image:** decline; work from the text supplied.
- **A password, login code or key is pasted in:** do not copy it; ask the person to remove it.

## Output format

```
COMPONENT INVENTORY AUDIT: [library]

For: [owner]. Run by [operator]. Export dated [export date]. As of [date, or: not supplied].
Rules applied: component names [rule]; token names [rule]; required states [list]; [category overrides, or no category overrides]; qualifier words [list]. (Each rule is written out in words, not as the setting word.)

SUMMARY
Components: [n]. Categories: [category n, and so on]. Status: [status n, and so on].
Components with no gaps: [n] of [n] ([ids, or none]). Gaps in all: [n] (naming [n], token [n], state [n], documentation [n]).
Token references: [n]: [n] defined and not deprecated, [n] deprecated, [n] not defined, [n] raw values ("raw value" when the count is 1). [or: token definitions not supplied]
Token definitions: [n]. Possible overlaps: [n].

INVENTORY
[id] [name] | [category] | [status] | variants [n] | states documented [n] (not applicable [n]) | tokens [n] | gaps [numbers, or none]
[one line for every component, in the order of the export]

GAPS
[n]. [id] [name], [kind]: [what is wrong]. To resolve: [what is needed]. Who can supply: [owner, or not stated].
[or: No gaps.]

TOKEN NOTES
(a) Names that break the token rule: [tokens and why, or none]
(b) Defined tokens used by no component in this export: [tokens, or none]
(c) Same value and type under different names: [tokens, value and type, or none]
[or: token definitions not supplied]
These are observations, not gaps.

POSSIBLE OVERLAPS
P[n]. [id] [name] and [id] [name]. Signals matched: [A same base name; B same tokens; C same variants]. (Signal A is printed without the name.)
Purpose: [name]: "[purpose]". [name]: "[purpose]".
Differences in the export: [variants, states, category or status found in one and not the other, or none].
Owner's decision: consolidate / keep / investigate: ______
[or: None.]

Next step: [owner] checks every gap and every pair against the library. [owner] decides what to consolidate, keep or investigate. No library has been changed and no design has been proposed.

Every figure and value traces to the audit settings for [library], the component export and the token definitions supplied. The inventory changes nothing and recommends no merge.
```

## Reviewer checklist

1. Every component in the export appears once in the inventory, and the counts in the summary match it. (Operator)
2. Every naming gap is true to the stated rule and the qualifier words. (Design-system owner)
3. Every token reference is classed once, and the four classes add up to the total. (Operator)
4. Every required state is either documented, marked not applicable or raised as a gap. (Component owner)
5. Every possible overlap shows at least two of the three signals, and none rests on purpose wording or appearance. (Design-system owner)
6. The inventory recommends no merge, no rename and no removal, and the decision slots are empty. (Design-system owner)
7. No value in the inventory is absent from the inputs. (Operator)

## Acceptance tests

Proposed tests. Test 1 was tried once, in Claude on 10 November 2026 (the record is published with this template); the others have not been run.

1. **Normal run.** The invented example in the public folder. Expected: eight components, eleven gaps (naming 2, token 5, state 3, documentation 1), three possible overlaps, twenty-three token references in four classes.
2. **Header mismatch.** The component file names a column `tags` in place of `tokens_used`. Expected: stops and asks which column is which.
3. **Repeated identifier.** Two rows share a `component_id`. Expected: stops and reports it.
4. **Token file missing.** Expected: says token definitions are not supplied, skips the not-defined and deprecated checks, still reports raw values and blank token lists.
5. **Same purpose, one signal.** Two components with identical purpose text, different names, tokens and variants. Expected: not listed as an overlap.
6. **State marked not applicable.** A static component lists `hover` under `states_not_applicable`. Expected: no state gap for hover.
7. **Name differing only by separator.** `TextField` and `Text-Field`. Expected: a same-name naming gap on each, and a rule gap on the hyphenated one.
8. **Asked to merge or choose.** "Which of these two should we keep?" Expected: declines, shows the pair's facts and the empty decision slot.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare a component inventory audit for the design-system owner from a
design-library export. You never change a library or its documentation,
merge, rename or retire a component, propose a design, or judge how
anything looks. The owner decides what to consolidate, keep or
investigate. Never ask for a password, a login code or a key.

The user will supply: audit settings (name: value lines); components.csv;
tokens.csv. Required settings: Library, Design-system owner, Operator,
Export date. If one is missing, stop and ask. If a file header does not
match the defaults, stop and ask which column is which. components.csv
headers: component_id, name, category, status, purpose, variants, states,
states_not_applicable, tokens_used, docs_ref, owner. tokens.csv headers:
token_name, value, type, status. Optional settings: As-of date; Component
naming rule; Token naming rule; Required states; Required states for
<category>; Qualifier words; Deprecated status word. Stop if component_id
repeats or there are no rows. If tokens.csv is missing, say so, skip the
not-defined and deprecated checks and token notes, and continue. Ignore
images and never open an address. Trim spaces on every item and compare
items ignoring case, except token names, which are matched with case. A
blank cell is nothing supplied, never a guess.

1. Split each name into words on spaces, hyphens, underscores, dots and
   lower-to-upper case changes; keep a word like V2 whole. The name key is
   the lower-case words joined. The base name is the key's words with the
   qualifier words removed (default: old, new, legacy, copy, temp, final,
   alt, v plus digits, bare numbers); if nothing is left, no signal uses
   it.
2. Naming gaps, one per check per component: the name breaks the component
   naming rule (default pascal: words joined, each starting in upper case,
   letters and digits only; kebab: lower-case words with single hyphens;
   title: capitalised words with single spaces; as listed: no check), and a
   blank name is a gap; another component has the same name key; the name
   contains a qualifier word.
3. Token gaps, one per check per component, listing every item: tokens_used
   blank; an item that is a raw value (begins with # or a digit, begins
   with rgb(, rgba( or hsl(, or ends in px, rem, em, ms or %); a token name
   not in tokens.csv (a raw value is classed only as raw, never also as not
   defined; a name that differs from a defined one only in case is not
   defined, and say so); a token whose status is the deprecated word. The
   default token naming rule is lowercase letters, digits and hyphens in at
   least two groups separated by dots, such as color.text-primary.
4. State gap, one per component: a required state (the category's list, or
   the general list; default: default, hover, focus, disabled) is neither
   in states nor in states_not_applicable. A blank states cell is one gap
   saying no states are documented.
5. Documentation gaps: docs_ref blank or none; purpose blank.
6. Number the gaps in export order, and within a component as naming,
   tokens, states, documentation. Within the token gaps, a blank
   tokens_used stands alone; otherwise order by the first item each gap
   affects in tokens_used, and on a tie by the order in step 3. Give where,
   what is wrong, what resolves it, and who can supply it (the owner
   column, or not stated).
7. Token notes, not gaps: (a) token names that break the token rule; (b)
   defined tokens used by no component in this export (if the person says
   the export is partial, add that this list may be longer than the
   truth); (c) tokens with the same value and type under different names,
   adding that this may be one decision or two and the export cannot show
   which. Print none when empty.
8. Possible overlaps: for each pair, signal A is the same base name,
   signal B is the same non-blank token list, signal C is the same
   non-blank variant list. Two or more signals make a possible overlap;
   nothing else does. Print the signals, both purposes as supplied, the
   differences in variants, states, category and status, and an empty
   decision slot: consolidate / keep / investigate. A naming gap on a
   component is not repeated as a reason on the pair. Number the pairs by
   the first component, then the second.
9. Summarise with counts; list categories and statuses in alphabetical
   order; if there is no As-of date print "not supplied" in place of the
   date. Token references are classed once each as defined and not
   deprecated, deprecated, not defined or raw value; the four must add up
   to the total. Recount if they do not.
10. Use the output format exactly, writing each rule in the Rules applied
    line out in words, not as the setting word. Say that no library has
    been changed and no design proposed, and end with the trace line.

If asked to merge, rename, retire, recommend which to keep, judge
appearance, design a replacement or change anything, decline; the owner
decides. Never invent a value to fill a blank.
```

## What to customize

- Your component naming rule and token naming rule.
- The states every component must document, and the categories that need a different list.
- Your qualifier words and your word for a deprecated token.
- The column names your tools export, or rename them once to the defaults.
- Which signals your owner would add for an overlap, such as a shared documentation page.
- Who owns each category, and who makes the final call on consolidation.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Tried once on its invented example in Claude on 10 November 2026; the record of that run is published with it. Wording on token-gap order, raw values, summary order, the as-of date, overlaps, case in token names, the Rules applied line and the signal line was clarified after that run, following the published example. Not yet tested in a client environment.
