# Component inventory audit: one trial on its example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the example in `public/example.md` (audit settings, components.csv with eight components, tokens.csv with ten tokens). No client data was used. The model that ran the trial did not write the template.

## What came out

The run followed the instruction block and the output format. In summary:

- Eight components; 11 gaps (naming 2, token 5, state 3, documentation 1); components with no gaps: C1 and C3.
- 23 token references: 19 defined and not deprecated, 1 deprecated (color.feedback-error), 2 not defined (color.tag-fill, on C6 and C7), 1 raw value (#1B7F4B). The four classes added up to 23.
- Gaps: C2 qualifier word "New"; C4 hyphen breaks PascalCase; C4 missing the input state "error"; C5 deprecated token; C5 raw value; C6 undefined token; C6 missing "focus" and "disabled"; C6 no documentation reference; C7 undefined token; C8 no tokens listed; C8 no states documented.
- Token notes: (a) Color.Surface-Alt breaks the token rule; (b) Color.Surface-Alt and space.control-padding are used by no component; (c) color.action-fill and color.feedback-info share #1D4ED8 (color), and space.control-pad and space.control-padding share 12px (space).
- Three possible overlaps: C1 Button and C2 ButtonNew (same base name, same tokens); C3 TextField and C4 Text-Input (same tokens, same variants); C6 Tag and C7 Chip (same tokens, same variants). Every owner's decision slot was left blank, and nothing recommended a merge, rename or removal.
- The closing line said no library was changed and no design proposed, followed by the trace line.

## What was observed

- **Every required part was produced:** summary, inventory line for each component, numbered gaps, three token notes, overlaps with blank decision slots, next step and trace line. Nothing in the instructions made the run stop.
- **Match with the published example:** the counts, gap numbering, token notes and the three overlap pairs agree with the published output. Differences were only in wording and ordering (below).
- **Reviewer checklist:** the seven checks held on this run. Every component appeared once; the four token classes summed to 23; each overlap showed at least two signals; no value appeared that is not in the inputs.
- **Disclosure about order of work:** the instruction was to read only the inputs before running. The first read of the example file also displayed the start of its published output (through the third gap). The counts and the rest of the output were worked out from the rules before reading on, and they agreed, but the run was not perfectly blind.
- **Ambiguities and guesses:**
  - The order of the categories and statuses in the summary is not stated. The published example lists them alphabetically; this run used order of first appearance in the export.
  - When one component has two gaps of the same kind (C5, deprecated and raw value), the order between them is not stated. The example follows the order of the items in `tokens_used`.
  - Whether a raw value such as #1B7F4B also counts as "not defined" is only implied by the rule that each reference is classed once. This run counted it as a raw value only.
  - "Token names default" in the Rules applied line: the template does not say whether to print the setting word or the expanded rule. The example prints the expanded rule.
  - The example's overlap line for P1 says "same base name (button)", with the name in brackets. The format does not ask for the name; this is an addition the format allows but does not require.
  - The format has no wording for the case where the as-of date is not supplied.
  - The base name compares after removing qualifier words, so ButtonNew and Button match; the template does not say whether a component's own qualifier gap should also appear as a reason on the overlap. It is left to the reader.
- **Facts not in the inputs:** none found in this output or in the published example. Every figure and value traces to the settings, components and tokens.
- **Limits:** this was one run, on sample data, in one product. It shows the instructions can be followed to a complete, checkable output. It does not show how they behave on a real library, a large export or other products.

## Since the trial

After this run and the independent review, the template was changed in these respects: summary order (alphabetical), the order of token gaps, classing a raw value only as raw, the as-of date wording and the qualifier gap not repeated on the pair were fixed before the review; the review then led to token names being matched with case, the Rules applied line being written out in words, and the signal line being printed without the base name (so the example's "(button)" was dropped). The ambiguities listed above are the observations of the run as it happened and are left as recorded. The template has not been re-run since these wording changes, which do not alter the example's inputs or output.
