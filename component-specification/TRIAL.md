# Component specification: tried on its example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the example in [the worked example](example.md): the settings, the approved design, the existing patterns, the notes and the constraints for an illustrative inline alert in an illustrative library. No client data was used. The run was made by a model that did not write the template.

## What came out

The template was amended after the first run, in response to review: the existing-pattern line now prints lists with commas between the names, the Overlap line has a fixed form, and notes set aside no longer count towards a topic. The output below is from a second run on the amended template, with the same inputs. The first run's output was the same except that the Banner line separated the names inside its lists with semicolons, as the earlier format did.

The assistant followed the instruction block and the output format on those inputs. This is the full output of the second run.

```
COMPONENT SPECIFICATION: Inline alert, Library R (an illustrative design library)

For: Design-system owner and Implementing engineer. Prepared 2026-11-10 by Design operations lead, from 8 design rows, 2 existing patterns, 7 notes, 2 constraints and the settings.
Column check: all headers matched.
Variants: 3. Required states: 9, of which 8 shown and 1 not shown. Distinct tokens: 10. Choices: 5. Set aside: 1.

PURPOSE AND CONTEXTS

Purpose: Shows a message next to the content it concerns.
Intended contexts: form field group; settings panel; page top.
Design reference: Inline alert design, version 2.

VARIANTS AND STATES

Required states: default; focus; hover.

info
  default: shown, "Blue bar with an information icon and one line of text".
  focus: shown, "Dismiss button shows a 2 px outline".
  hover: shown, "Dismiss button darkens".
  Also shown: none.
  Tokens: color.alert-info-bg; color.alert-info-text; space.alert-pad; color.focus-ring; color.alert-info-hover.
warning
  default: shown, "Amber bar with a warning icon and one line of text".
  focus: shown, "Dismiss button shows a 2 px outline".
  hover: not shown in the approved design. C1.
  Also shown: none.
  Tokens: color.alert-warn-bg; color.alert-warn-text; space.alert-pad; color.focus-ring.
error
  default: shown, "Red bar with an error icon and up to two lines of text".
  focus: shown, "Dismiss button shows a 2 px outline".
  hover: shown, "Dismiss button darkens".
  Also shown: none.
  Tokens: color.alert-error-bg; color.alert-error-text; space.alert-pad; color.focus-ring; color.alert-error-hover.

Tokens are printed as supplied. No token list was given, so none was checked.

USAGE RULES

use: N1 (all): Use beside the content the message concerns.
avoid: not supplied. C2.
placement: N2 (all): Directly above the field group it refers to.
content: N3 (error): Up to two lines of text.

ACCESSIBILITY NOTES

name: N4 (all): The dismiss button is labelled Dismiss message.
keyboard: N5 (all): The dismiss button is reached with Tab and activated with Enter or Space.
focus: N6 (all): The dismiss button shows a 2 px outline when focused.
announcement: not supplied. C3.
colour: N7 (all): Every message starts with an icon and the word Information; Warning or Error.
target: not supplied. C4.

ENGINEERING CONSTRAINTS

K1 (all): Must display on the legacy settings page without scripted animation.

EXISTING PATTERNS

Banner (D-07): purpose "Shows a message about the whole page"; contexts page top, site header; variants info, warning; states default, focus; usage rule "One message per page".
  Overlap: shares the context "page top" with Inline alert. C5.
  Variants only in Inline alert: error. Variants only in Banner: none.
  States only in Inline alert: hover. States only in Banner: none.
Toast (D-31): no overlap found on name, purpose or context.

CHOICES FOR THE DESIGN OWNER

C1 warning, hover: The approved design shows no hover state for warning, and the required states include it. Add it to the design, or mark it not applicable for warning.
  Status: Open. Choice: ______ Chosen by: ______ Date: ______
C2 usage, avoid: No note supplied on when not to use Inline alert. What should the rule say?
  Status: Open. Choice: ______ Chosen by: ______ Date: ______
C3 accessibility, announcement: No note supplied on how a change appearing is made known to assistive technology. What should the note say?
  Status: Open. Choice: ______ Chosen by: ______ Date: ______
C4 accessibility, target: No note supplied on the size of anything a person presses. What should the note say?
  Status: Open. Choice: ______ Chosen by: ______ Date: ______
C5 existing pattern, Banner: Inline alert and Banner share the context "page top". Extend Banner, keep both with a rule that separates them, or retire one.
  Status: Open. Choice: ______ Chosen by: ______ Date: ______

SET ASIDE

K2: names the variant "success", which the approved design does not contain. Which variant is meant?

SIGN-OFF

Design-system owner: has made every choice and approves this specification: ______ Date: ______
Implementing engineer: confirms all 5 choices are made and every set-aside line is dealt with: ______ Date: ______

Draft for the Design-system owner. No component has been created or changed, no state or rule has been invented, and nothing has been sent.
```

## What was observed

- **Every required part was produced.** All sections of the output format appear, in order. The counts add up: 3 variants times 3 required states is 9, with 8 shown and 1 not shown. There are 5 choices (one state, one usage topic, two accessibility topics, one existing pattern) and 1 set-aside line.
- **Nothing stopped the run.** All headers matched, no variant and state repeated, no id or pattern name repeated, and every note topic was in the list. No stop condition applied.
- **Differences from the published example: none.** The output matches the example's specification line for line.
- **A caution about that match.** The example's output was displayed in the same step that showed the inputs, so the assistant saw it before producing its own. The inputs were used as instructed, but the match cannot count as an independent reproduction. A fresh run that has not seen the example would be a better test.
- **Facts not in the inputs: none found** in either output. Every quoted description, note, constraint, token and pattern line is in the supplied files. The words added are the fixed wording and the labels of the format.
- **Where the instructions needed a judgement** (recorded at the first run; the points marked answered were settled by the amendments made afterwards, and the amended template has not been run again on an input that tests them):
  - "Distinct tokens" is not defined as per variant or across all variants. The count of 10 treats it as across all variants. The example does the same. Answered: the template now says distinct tokens are counted across all variants, each name once.
  - "States only in [component]" does not say whether the component's states are those the design shows or the required list. The run used the states the design shows. Here both give the same answer. Answered: the template now says the states the design shows are used.
  - The template says to print notes and descriptions word for word, but the format puts a full stop after them. A full stop was added outside the quotation marks for descriptions and after notes and constraints, which already read as complete lines. The purpose, supplied without a full stop, also had one added. Answered: the template now says where the full stop goes.
  - The format shows "Extra columns ignored" as optional text. There were none, so the line was left out.
  - Contexts and variants of an existing pattern are separated by semicolons in the file and printed with semicolons in a line that also uses semicolons between fields. The line is readable but the boundaries between fields are not clear. Answered: the lists are now printed with commas, and this run did so.
  - The fixed line "No token list was given, so none was checked" is printed even though the settings never mention a token list. It is harmless but not explained. Answered: the template now says a token list is not part of its work.
  - The closing line says "Draft for the Design-system owner", using the role text from the settings. That follows the template.
- **Fixed form of the Overlap line:** this run used the fixed form added after the first run. The first run had no fixed form and happened to word it the same way.
- **Not exercised:** the stop conditions, the "Also shown" line with a real state, an optional file left out, a duplicate row and the refusal wording. The acceptance tests for those remain unrun.
- **Not tested:** these were two runs on one example in one product. It says nothing about a real design library or about how other products would handle the template.
