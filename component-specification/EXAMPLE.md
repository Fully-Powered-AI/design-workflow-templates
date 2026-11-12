# Component specification: an invented example

*Illustrative example with invented data.* The library, the product, the component, the patterns and every token and note below are invented. Library R belongs to an invented invoicing product. The design operations lead ran the workflow template after the design-system owner approved a design for an inline alert. First come the inputs the lead supplied, in full, then the specification the workflow template returned.

## The inputs

### 1. Settings

```
Library: Library R (an invented design library)
Component: Inline alert
Design reference: Inline alert design, version 2
Purpose: Shows a message next to the content it concerns
Intended contexts: form field group; settings panel; page top
Required states: default; focus; hover
Design-system owner: Design-system owner
Engineer: Implementing engineer
Operator: Design operations lead
Today: 2026-11-10
```

### 2. Approved design (design.csv)

```
variant,state,description,tokens
info,default,Blue bar with an information icon and one line of text,color.alert-info-bg; color.alert-info-text; space.alert-pad
info,focus,Dismiss button shows a 2 px outline,color.focus-ring
info,hover,Dismiss button darkens,color.alert-info-hover
warning,default,Amber bar with a warning icon and one line of text,color.alert-warn-bg; color.alert-warn-text; space.alert-pad
warning,focus,Dismiss button shows a 2 px outline,color.focus-ring
error,default,Red bar with an error icon and up to two lines of text,color.alert-error-bg; color.alert-error-text; space.alert-pad
error,focus,Dismiss button shows a 2 px outline,color.focus-ring
error,hover,Dismiss button darkens,color.alert-error-hover
```

### 3. Existing patterns (patterns.csv)

```
pattern,purpose,contexts,variants,states,usage_rule,reference
Banner,Shows a message about the whole page,page top; site header,info; warning,default; focus,One message per page,D-07
Toast,Brief message after an action,after save; after send,info; success; error,default,Disappears on its own,D-31
```

### 4. Notes (notes.csv)

```
note_id,topic,applies_to,note
N1,use,all,Use beside the content the message concerns
N2,placement,all,Directly above the field group it refers to
N3,content,error,Up to two lines of text
N4,name,all,The dismiss button is labelled Dismiss message
N5,keyboard,all,The dismiss button is reached with Tab and activated with Enter or Space
N6,focus,all,The dismiss button shows a 2 px outline when focused
N7,colour,all,Every message starts with an icon and the word Information; Warning or Error
```

### 5. Constraints (constraints.csv)

```
constraint_id,applies_to,constraint
K1,all,Must display on the legacy settings page without scripted animation
K2,success,Message text is limited to 160 characters
```

## The specification

```
COMPONENT SPECIFICATION: Inline alert, Library R (an invented design library)

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
