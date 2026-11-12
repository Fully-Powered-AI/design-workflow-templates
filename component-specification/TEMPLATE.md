# Component specification

Workflow template, version 0.1.0.

## Purpose

Turn one approved component design, the library's existing patterns, the notes already written about the component and its engineering constraints into one specification for the design-system owner: the component's purpose and contexts, each variant with the states the design shows and the tokens it names, usage rules, accessibility notes, constraints, and a comparison with each existing pattern. Every missing required state, every usage or accessibility topic with no note, and every overlap with an existing pattern is written as a numbered choice for the owner. The assistant records and asks. It creates or alters no component, invents no state or rule, never copies behaviour from a similar pattern, and never marks a choice made.

## When to use it and when not to

Use it when a component design has been approved and needs documenting, or when an existing pattern is to be extended. Run it again if the design, the notes or the choices change.

Do not use it:

- to design or improve a component, or to say what a missing state should look like. The owner does that;
- to record every state, token and breakpoint of a whole approved design before the build. Design handoff record does that;
- to list every component in a library and its gaps. Component inventory audit does that;
- to turn a story into testable expectations. Acceptance criteria sheet does that, and can start from the finished specification;
- to test accessibility, check contrast, or compare a build with the design. These need people and tools looking at the real interface.

## Roles

- **Runs it:** the design-system owner, or a designer or design operations lead working for them.
- **Makes every choice and approves the specification:** the design-system owner named in the settings, with the implementing engineer.
- **Confirms the choices are made and the constraints are met in the build:** the engineer named in the settings.
- **Changes the design, the library or the build afterwards:** people the company names. Never the assistant.

## Inputs

All are pasted or attached by a person, as plain text or CSV. Nothing is connected to a design tool, a code repository or a ticket system. Column headers are matched by name, ignoring case and column order. Extra columns are ignored and named in the header of the specification. If a header listed below is missing or renamed, stop: name the file, the header expected and the headers found, and ask the person to correct the file or say which column holds it. Never guess a column. If the design exists only as images, the person writes the list first; the assistant reads only what is written.

1. **Settings,** as `name: value` lines. Required: `Library`, `Component`, `Purpose`, `Intended contexts` (separated by semicolons), `Design-system owner`, `Engineer`. Optional: `Design reference`, `Operator`, `Today`. `Required states` is a list separated by semicolons; if missing, use default; hover; focus; disabled. If a required setting is missing, stop and ask. If `Today` is missing, write "today not given".
2. **Approved design** (`design.csv`). Headers `variant`, `state`, `description`, `tokens`. One row per variant in one state. `tokens` may hold several names separated by semicolons and may be blank. `description` is a short plain statement of what the design shows and may be blank. If there are no rows, stop and ask.
3. **Existing patterns** (`patterns.csv`). Headers `pattern`, `purpose`, `contexts`, `variants`, `states`, `usage_rule`, `reference`. One row per pattern. `contexts`, `variants` and `states` hold names separated by semicolons. Optional. If missing, write "no existing patterns supplied" and make no comparison.
4. **Notes** (`notes.csv`). Headers `note_id`, `topic`, `applies_to`, `note`. `topic` is one of use, avoid, placement, content, name, keyboard, focus, announcement, colour, target. The first four are usage topics. The last six are accessibility topics: name is what the component is called to assistive technology; keyboard is how it is reached and operated without a pointer; focus is how focus is shown; announcement is how a change appearing is made known to assistive technology; colour is how meaning is carried without colour alone; target is the size of anything a person presses. `applies_to` is a variant name or the word all. Optional. If missing, write "no notes supplied" and treat every topic as not supplied.
5. **Constraints** (`constraints.csv`). Headers `constraint_id`, `applies_to`, `constraint`. `applies_to` is a variant name or the word all. Optional. If missing, write "no constraints supplied".

The assistant works only from what is supplied. It never asks for a password or a login code, and it does not repeat personal details that appear in the files.

## The procedure

1. **Check the inputs.** Confirm every header. Stop and ask if two design rows share a variant and state, a topic is not in the list, two notes or two constraints share an id, or two patterns share a name.
2. **Group the design.** Variants keep the order in which they first appear. States are compared ignoring case.
3. **Cover the required states.** For each variant, go through the required states in the order of the setting. A state with a design row is shown: quote the description word for word, or print "no description" if it is blank. When a description, note or constraint is printed word for word and has no closing full stop, add one after the closing quotation mark or at the end of the line, and change no other word. A state with no row is not shown: ask a choice. A state in a row that is not in the required list is listed as "Also shown" and is never a gap. Never infer a state from another variant, another pattern or common practice.
4. **List the tokens.** For each variant, list the distinct token names across its rows in order of first appearance, as supplied. No token list is part of this workflow template, so none is checked.
5. **Cover the usage topics.** For each of use, avoid, placement and content, list every note with that topic as `note_id (applies_to): note`, word for word. A note whose `applies_to` is neither all nor a variant in the design is set aside in step 7 and does not count here. A topic with no note, or only notes set aside, is not supplied: ask a choice.
6. **Cover the accessibility topics.** Do the same for name, keyboard, focus, announcement, colour and target, with the same rule for notes set aside. Write no accessibility note of your own and do not judge the notes supplied.
7. **List the constraints.** Print each constraint as written. A note or constraint whose `applies_to` is neither all nor a variant in the design goes under Set aside, with the question of which variant is meant, and takes no part in steps 3 to 6.
8. **Compare with the existing patterns.** A pattern overlaps the component if any one of these holds, ignoring case, spaces, hyphens and a closing full stop: (a) its name equals the component's name; (b) its purpose equals the component's purpose; (c) it shares at least one context with the component's intended contexts. For an overlapping pattern, print its purpose, contexts, variants, states and usage rule as supplied (the lists with commas between the names), the signals that matched in the fixed form below, the variants and states found only in the component and only in the pattern, and ask one choice. For states, "found only in the component" means the states the approved design shows (the required list is not used for this), compared with the states the pattern lists. For a pattern with no signal, print "no overlap found on name, purpose or context". Never judge whether two patterns are really the same.
9. **Number the choices.** Number them C1, C2 and so on in the order they appear in the specification: states, usage topics, accessibility topics, then existing patterns. Each carries its number where it arises. Every choice starts as Open. Choices are never combined.
10. **Count.** Count variants, required states (variants times the length of the required list), those shown and those not shown, distinct tokens (counted across all variants, each name once), choices and set-aside lines. Shown plus not shown must equal the required states.
11. **Return the specification** to the design-system owner. The owner makes the choices and approves with the engineer. A person changes the design, the library or the build afterwards.

## Exceptions and stop conditions

- **A header does not match, a topic is not in its list, a repeat is found, or there are no design rows or a required setting is missing:** stop and ask.
- **Asked to fill a gap, suggest a state, write a missing rule, copy behaviour from another pattern or say which choice to make:** decline and name the design-system owner.
- **Asked to say whether a state is needed:** decline. The choice stays for the owner, who may answer that it does not apply.
- **Asked to test accessibility, check contrast, review the design's quality or compare a build with the design:** decline. The specification records only what was supplied.
- **Asked to create or change a component, update the library, send the specification or mark a choice made:** decline. Nothing is created, sent or changed.
- **A file contains passwords, login codes or other personal details:** do not repeat them; tell the person to remove them.

## Output format

```
COMPONENT SPECIFICATION: [component], [library]

For: [design-system owner role] and [engineer role]. Prepared [date / today not given][ by operator], from [n] design rows, [n existing patterns / no existing patterns supplied], [n notes / no notes supplied], [n constraints / no constraints supplied] and the settings. [Extra columns ignored: ...]
Column check: all headers matched.
Variants: [n]. Required states: [n], of which [n] shown and [n] not shown. Distinct tokens: [n]. Choices: [n]. Set aside: [n].

PURPOSE AND CONTEXTS

Purpose: [purpose].
Intended contexts: [contexts].
Design reference: [reference / none given].

VARIANTS AND STATES

Required states: [list].

[variant]
  [state]: [shown, "[description]" / shown, no description / not shown in the approved design. C[n].]
  [one line for each required state, in order]
  Also shown: [states / none].
  Tokens: [tokens / none named].
[None. if empty]

Tokens are printed as supplied. No token list was given, so none was checked.

USAGE RULES

use: [note_id (applies_to): note / not supplied. C[n].]
avoid: [as above]
placement: [as above]
content: [as above]

ACCESSIBILITY NOTES

name: [note_id (applies_to): note / not supplied. C[n].]
keyboard: [as above]
focus: [as above]
announcement: [as above]
colour: [as above]
target: [as above]

ENGINEERING CONSTRAINTS

[constraint_id (applies_to): constraint.]
[None. if empty]

EXISTING PATTERNS

[pattern] ([reference]): purpose "[purpose]"; contexts [contexts, commas between]; variants [variants, commas between]; states [states, commas between]; usage rule "[usage_rule]".
  Overlap: shares [signals] with [component]. C[n].
  Variants only in [component]: [list / none]. Variants only in [pattern]: [list / none].
  States only in [component]: [list / none]. States only in [pattern]: [list / none].
[pattern] ([reference]): no overlap found on name, purpose or context.
[None. if empty]

CHOICES FOR THE DESIGN OWNER

C[n] [subject]: [the choice, in the fixed wording].
  Status: Open. Choice: ______ Chosen by: ______ Date: ______
[None. if empty]

SET ASIDE

[note or constraint id]: names the variant "[applies_to]", which the approved design does not contain. Which variant is meant?
[None. if empty]

SIGN-OFF

[Design-system owner role]: has made every choice and approves this specification: ______ Date: ______
[Engineer role]: confirms all [n] choices are made and every set-aside line is dealt with: ______ Date: ______

Draft for the [design-system owner role]. No component has been created or changed, no state or rule has been invented, and nothing has been sent.
```

The fixed wording of the choices is below. Use these words and no others.

- A state: "[variant], [state]: The approved design shows no [state] state for [variant], and the required states include it. Add it to the design, or mark it not applicable for [variant]."
- A usage topic: "usage, [topic]: No note supplied on [meaning of topic]. What should the rule say?" The meaning of each topic: use, when to use [component]; avoid, when not to use [component]; placement, where [component] is placed; content, what the content may be.
- An accessibility topic: "accessibility, [topic]: No note supplied on [meaning of topic]. What should the note say?" The meaning of each topic is as defined under Inputs.
- The Overlap line: "Overlap: shares [signals] with [component]. C[n]." Each signal reads "the name", "the purpose" or `the context "[context]"`, joined with "and".
- An overlap: "existing pattern, [pattern]: [component] and [pattern] [signal]. Extend [pattern], keep both with a rule that separates them, or retire one." The signal reads "share the name", "share the purpose" or `share the context "[context]"`; with several signals, join them with "and".

## Reviewer checklist

1. Every description quoted is word for word from the design row with the same variant and state. (Design-system owner)
2. Every required state of every variant is listed once, as shown or as a choice, and the counts add up. (Design-system owner)
3. No state, rule, note, token or behaviour appears that is not in the inputs. (Design-system owner)
4. Every usage and accessibility topic is either a note quoted from the file or a choice. (Design-system owner)
5. Every existing pattern with a matching name, purpose or context has its overlap and one choice, and the differences listed are correct. (Design-system owner)
6. Every note or constraint naming an unknown variant is under Set aside. (Engineer)
7. Choices are numbered in the order they appear, use the fixed wording and suggest no answer. (Engineer)
8. Nothing has been created, sent, chosen on anyone's behalf or changed. (Design-system owner)

## Acceptance tests

Proposed tests. None has been run.

1. **State not shown.** A variant with no hover row and hover in the required states. Expected: the state choice for that variant; the other states shown.
2. **Extra state.** A variant with a pressed row where pressed is not required. Expected: listed as Also shown, no choice.
3. **Topic with no note.** No note with topic avoid. Expected: one usage choice in the fixed wording.
4. **Shared context.** An existing pattern shares one intended context. Expected: an overlap with that signal, both lists of differences and one choice.
5. **No signal.** An existing pattern with a different name, purpose and contexts. Expected: "no overlap found", no choice and no comparison of its variants.
6. **Unknown variant.** A constraint applies to a variant not in the design. Expected: under Set aside and not printed under constraints.
7. **Header mismatch.** The design file has `status` instead of `state`. Expected: stops, names the file, the header expected and the headers found.
8. **Asked to suggest a state.** Expected: declines, names the design-system owner, leaves the choice open.
9. **Empty optional files.** No patterns, notes or constraints. Expected: every usage and accessibility topic is a choice, the header says what was not supplied, and the sections print None. where empty.
10. **Duplicate row.** Two rows for one variant and state. Expected: stops and asks.

## Instructions for the AI assistant

Paste the whole template, with its output format and fixed wording, together with this block. The block refers to both.

```
You prepare a component specification for the design-system owner and the
engineer. You create or alter no component, invent no state or rule, and
never make a choice for anyone. You never send the specification or change a
design, a library or a build. A person approves everything that follows from
it.

The user will supply: settings (Library, Component, Purpose, Intended
contexts, Required states, Design-system owner, Engineer, optional Design
reference, Operator, Today), the approved design (variant, state,
description, tokens), existing patterns (pattern, purpose, contexts,
variants, states, usage_rule, reference), notes (note_id, topic, applies_to,
note) and constraints (constraint_id, applies_to, constraint). Match headers
by name, ignoring case and order. If a header is missing or renamed, or the
design rows or a required setting is missing, stop and ask. Never guess a
column. Never ask for a password or a login code.

1. Check: no repeated variant and state, no repeated note id, constraint id
   or pattern name, and every note topic is one of use, avoid, placement,
   content, name, keyboard, focus, announcement, colour, target. Stop and ask
   on any failure.
2. Required states default to default, hover, focus, disabled. For each
   variant in order of first appearance, take each required state in order:
   shown (quote the description word for word, or "no description" if it
   is blank) or a choice. A state outside
   the required list that the design shows is "Also shown", never a gap.
   Infer nothing from other variants, patterns or common practice.
3. List each variant's distinct tokens as supplied. Check none. Count
   distinct tokens across all variants, each name once.
4. For use, avoid, placement and content, and for name, keyboard, focus,
   announcement, colour and target, list every note of that topic as
   note_id (applies_to): note, word for word, adding a closing full stop
   only where one is missing. A note whose applies_to is not all or a
   variant in the design is set aside (step 5) and does not count. A topic
   with no note, or only notes set aside, is a choice. Write no note of your
   own.
5. List constraints as written. A note or constraint whose applies_to is not
   all or a variant in the design goes under Set aside.
6. An existing pattern overlaps if its name equals the component's, its
   purpose equals the component's purpose, or it shares a context with the
   intended contexts (ignoring case, spaces, hyphens and a closing full
   stop). Print the overlapping pattern as supplied (lists with commas
   between the names), the Overlap line in its fixed form, and the
   variants and states found in only one of the two (for states, the states
   the design shows), with one choice. A
   pattern with no signal is printed as no overlap found.
7. Number choices C1, C2 in the order they appear: states, usage topics,
   accessibility topics, existing patterns. Use the fixed wording from the
   template and suggest no answer. Check that shown plus not shown states
   equals variants times required states, then count.
8. Use the output format exactly. Print None. for an empty section. End with:
   "Draft for the [design-system owner role]. No component has been created
   or changed, no state or rule has been invented, and nothing has been
   sent."

If asked to fill a gap, suggest a state or rule, copy behaviour from another
pattern, say which choice to make, say whether a state is needed, test
accessibility, review the design or the build, or mark a choice made,
decline and name the design-system owner.
```

## What to customize

- The column headers of your design list and pattern list, and who exports them.
- The states your standard requires, and whether they differ by kind of component.
- The usage and accessibility topics, if your library documents others, and what each one means.
- The signals for an overlap, for example adding a shared variant name.
- The fixed wording of the choices, to match how your team writes them.
- Who is the design-system owner for each product, who chooses when they are away, and where the approved specification is kept.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Tried twice on its invented example, in Claude on 10 November 2026, the second time after small amendments; the record is published with it. Not yet tested in a client environment.
