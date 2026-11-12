# Component inventory audit: an invented example

*Illustrative example with invented data.* The library, the product, the teams and every component, token and figure below are invented. Library Q belongs to an invented invoicing app. The design operations lead ran the workflow template once the design-system owner had scheduled a quarterly review. First come the inputs the lead supplied, in full, then the inventory the workflow template returned.

## The inputs

### 1. Audit settings

```
Library: Library Q (an invented design library)
Design-system owner: Design-system owner
Operator: Design operations lead
Export date: 2026-11-03
As-of date: 2026-11-10
Component naming rule: pascal
Token naming rule: default
Required states: default; hover; focus; disabled
Required states for input: default; focus; disabled; error
Qualifier words: default
Deprecated status word: deprecated
```

### 2. Components (components.csv)

```
component_id,name,category,status,purpose,variants,states,states_not_applicable,tokens_used,docs_ref,owner
C1,Button,action,stable,Starts or confirms an action,primary; secondary; destructive,default; hover; focus; disabled,,color.action-fill; color.text-on-action; space.control-pad; radius.control,D-12,Core team
C2,ButtonNew,action,experimental,Starts or confirms an action; replacement under trial,primary; secondary,default; hover; focus; disabled,,color.action-fill; color.text-on-action; space.control-pad; radius.control,D-14,Core team
C3,TextField,input,stable,Single-line text entry,default; with-icon,default; focus; disabled; error,,color.border-input; color.text-primary; space.control-pad; radius.control,D-20,Forms team
C4,Text-Input,input,stable,Single-line text entry,default; with-icon,default; focus; disabled,,color.border-input; color.text-primary; space.control-pad; radius.control,D-21,Forms team
C5,Toast,feedback,stable,Brief message after an action,info; success; error,default,hover; focus; disabled,color.feedback-info; color.feedback-error; #1B7F4B,D-31,Core team
C6,Tag,display,stable,Labels an item with a short category,neutral; positive,default; hover,,color.tag-fill; color.text-primary,none,Content team
C7,Chip,display,stable,Labels an item with a short category,neutral; positive,default; hover; focus; disabled,,color.tag-fill; color.text-primary,D-33,Content team
C8,Dialog,overlay,stable,Asks for a decision before work continues,confirm; alert,,,,D-40,Core team
```

### 3. Token definitions (tokens.csv)

```
token_name,value,type,status
color.action-fill,#1D4ED8,color,active
color.text-on-action,#FFFFFF,color,active
color.text-primary,#111827,color,active
color.border-input,#9CA3AF,color,active
color.feedback-info,#1D4ED8,color,active
color.feedback-error,#B42318,color,deprecated
space.control-pad,12px,space,active
radius.control,6px,radius,active
Color.Surface-Alt,#F3F4F6,color,active
space.control-padding,12px,space,active
```

## The inventory

```
COMPONENT INVENTORY AUDIT: Library Q (an invented design library)

For: Design-system owner. Run by Design operations lead. Export dated 2026-11-03. As of 2026-11-10.
Rules applied: component names PascalCase; token names default (lowercase letters, digits and hyphens, in at least two groups separated by dots); required states default, hover, focus, disabled; input: default, focus, disabled, error; qualifier words old, new, legacy, copy, temp, final, alt, v plus digits, bare numbers.

SUMMARY
Components: 8. Categories: action 2, display 2, feedback 1, input 2, overlay 1. Status: experimental 1, stable 7.
Components with no gaps: 2 of 8 (C1, C3). Gaps in all: 11 (naming 2, token 5, state 3, documentation 1).
Token references: 23: 19 defined and not deprecated, 1 deprecated, 2 not defined, 1 raw value.
Token definitions: 10. Possible overlaps: 3.

INVENTORY
C1 Button | action | stable | variants 3 | states documented 4 (not applicable 0) | tokens 4 | gaps none
C2 ButtonNew | action | experimental | variants 2 | states documented 4 (not applicable 0) | tokens 4 | gaps 1
C3 TextField | input | stable | variants 2 | states documented 4 (not applicable 0) | tokens 4 | gaps none
C4 Text-Input | input | stable | variants 2 | states documented 3 (not applicable 0) | tokens 4 | gaps 2, 3
C5 Toast | feedback | stable | variants 3 | states documented 1 (not applicable 3) | tokens 3 | gaps 4, 5
C6 Tag | display | stable | variants 2 | states documented 2 (not applicable 0) | tokens 2 | gaps 6, 7, 8
C7 Chip | display | stable | variants 2 | states documented 4 (not applicable 0) | tokens 2 | gaps 9
C8 Dialog | overlay | stable | variants 2 | states documented 0 (not applicable 0) | tokens 0 | gaps 10, 11

GAPS
1. C2 ButtonNew, naming: the name contains the qualifier word "New". To resolve: confirm whether this is a replacement under trial or a copy to retire, and the name it should carry. Who can supply: Core team.
2. C4 Text-Input, naming: the name is not PascalCase because it contains a hyphen. To resolve: the name the library intends, or confirmation that the exception is deliberate. Who can supply: Forms team.
3. C4 Text-Input, state: required state "error" for input is not documented and not marked not applicable. To resolve: document the state or mark it not applicable. Who can supply: Forms team.
4. C5 Toast, token: uses color.feedback-error, whose status in the token file is deprecated. To resolve: which token replaces it. Who can supply: Core team.
5. C5 Toast, token: lists "#1B7F4B", a raw value, in place of a token name. To resolve: the token that value stands for, or a decision to define one. Who can supply: Core team.
6. C6 Tag, token: color.tag-fill is not defined in the token file. To resolve: the definition, or the token it should use. Who can supply: Content team.
7. C6 Tag, state: required states "focus" and "disabled" are not documented and not marked not applicable. To resolve: document them or mark them not applicable. Who can supply: Content team.
8. C6 Tag, documentation: no documentation reference (docs_ref is none). To resolve: the reference to its documentation. Who can supply: Content team.
9. C7 Chip, token: color.tag-fill is not defined in the token file. To resolve: the definition, or the token it should use. Who can supply: Content team.
10. C8 Dialog, token: no tokens are listed. To resolve: the tokens the component uses, or confirmation that it uses none. Who can supply: Core team.
11. C8 Dialog, state: no states are documented; the required states are default, hover, focus and disabled. To resolve: document them or mark each not applicable. Who can supply: Core team.

TOKEN NOTES
(a) Names that break the token rule: Color.Surface-Alt (contains upper-case letters).
(b) Defined tokens used by no component in this export: Color.Surface-Alt; space.control-padding.
(c) Same value and type under different names: color.action-fill and color.feedback-info (#1D4ED8, color); space.control-pad and space.control-padding (12px, space). This may be one decision or two; the export cannot show which.
These are observations, not gaps.

POSSIBLE OVERLAPS
P1. C1 Button and C2 ButtonNew. Signals matched: A same base name; B same tokens.
Purpose: Button: "Starts or confirms an action". ButtonNew: "Starts or confirms an action; replacement under trial".
Differences in the export: variants only in Button: destructive. Status: Button stable, ButtonNew experimental.
Owner's decision: consolidate / keep / investigate: ______

P2. C3 TextField and C4 Text-Input. Signals matched: B same tokens; C same variants.
Purpose: TextField: "Single-line text entry". Text-Input: "Single-line text entry".
Differences in the export: states documented only in TextField: error.
Owner's decision: consolidate / keep / investigate: ______

P3. C6 Tag and C7 Chip. Signals matched: B same tokens; C same variants.
Purpose: Tag: "Labels an item with a short category". Chip: "Labels an item with a short category".
Differences in the export: states documented only in Chip: focus, disabled.
Owner's decision: consolidate / keep / investigate: ______

Next step: Design-system owner checks every gap and every pair against the library. Design-system owner decides what to consolidate, keep or investigate. No library has been changed and no design has been proposed.

Every figure and value traces to the audit settings for Library Q (an invented design library), the component export and the token definitions supplied. The inventory changes nothing and recommends no merge.
```
