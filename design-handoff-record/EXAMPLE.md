# Design handoff record: an invented example

*Illustrative example with invented data.* The company, the product and every detail are made up. A design owner at an invented parcel-tracking company, Quillon Parcels, is handing one approved screen to the engineer who will build it.

## What the person supplies

**Settings:** product Quillon Parcels customer web app; design Track a parcel, version 3; smallest supported width 360 px; breakpoints Small from 360, Medium from 768, Large from 1200; design owner and engineer as roles; today 2026-11-10.

**Design inventory** (`item_id,screen,width,component,kind,state,content,tokens,description`):

```
D1,Track a parcel,1280,Tracking field,Field,default,Tracking number,color.text.default; space.4,Label above a single-line input
D1,Track a parcel,390,Tracking field,Field,default,Tracking number,color.text.default; space.4,Same field at full width
D1,Track a parcel,1280,Tracking field,Field,error,Tracking number,color.text.error; space.4,Red outline and the message We cannot find that number under the input
D2,Track a parcel,1280,Track button,Control,default,,color.action.primary; space.5,Filled button labelled Track beside the field
D2,Track a parcel,1280,Track button,Control,disabled,,color.action.disabled,Grey button while the field is empty
D3,Track a parcel,1280,Delivery timeline,Data,default,Carrier note; Status label,space.6; color.text.default,Up to five events newest first with a note under each
D3,Track a parcel,390,Delivery timeline,Data,default,Carrier note; Status label,space.6; color.text.default,Events stack with the date above the status
D3,Track a parcel,320,Delivery timeline,Data,default,Carrier note; Status label,space.6; color.text.default,Events stack with the date above the status
```

**Component references** (`component,states_documented,reference`):

```
Tracking field,default; hover; focus; error,Design library Text field
Track button,default; hover; focus; pressed; disabled; loading,Design library Button
Delivery timeline,default; loading; empty,Design library Timeline
```

**Tokens** (`token,value,used_for`):

```
color.text.default,#1F2933,Body text
color.text.error,#B42318,Error messages
color.action.primary,#1456C8,Main buttons
color.action.disabled,#C9CED6,Disabled controls
space.4,16px,Gaps inside forms
space.6,24px,Gaps between list items
```

**Content rules** (`rule_id,applies_to,max_length,overflow,format`):

```
R1,Tracking number,24,scroll within the field,letters and digits only
R2,Carrier note,,wrap,
```

**Interaction decisions** (`decision_id,item_id,trigger,result`):

```
I1,D2,Tap Track with a number entered,The delivery timeline for that number appears
I2,D9,Tap Share,The share sheet opens
```

## The record

```
DESIGN HANDOFF RECORD: Quillon Parcels customer web app, Track a parcel version 3

For: the design owner and the engineer. Prepared: 2026-11-10, from 8 inventory rows, 3 component references, 6 tokens, 2 content rules, 2 interaction decisions and the settings.
Column check: all headers matched.
Items: 3 on 1 screen(s). Required states: 13 covered, 2 unstated. Questions: 7. Set aside: 2.

ITEMS

Track a parcel
D1 Tracking field (Field); component reference: Design library Text field.
  default: shown at 1280, "Label above a single-line input"; shown at 390, "Same field at full width"
  hover: component library only (Design library Text field)
  focus: component library only (Design library Text field)
  disabled: Q1
  error: shown at 1280, "Red outline and the message We cannot find that number under the input"
  Also shown: none.
  Tokens: color.text.default = #1F2933; space.4 = 16px; color.text.error = #B42318.
D2 Track button (Control); component reference: Design library Button.
  default: shown at 1280, "Filled button labelled Track beside the field"
  hover: component library only (Design library Button)
  focus: component library only (Design library Button)
  pressed: component library only (Design library Button)
  disabled: shown at 1280, "Grey button while the field is empty"
  loading: component library only (Design library Button)
  Also shown: none.
  Tokens: color.action.primary = #1456C8; space.5: Q2; color.action.disabled = #C9CED6.
D3 Delivery timeline (Data); component reference: Design library Timeline.
  default: shown at 1280, "Up to five events newest first with a note under each"; shown at 390, "Events stack with the date above the status"
  loading: component library only (Design library Timeline)
  empty: component library only (Design library Timeline)
  error: Q3
  Also shown: none.
  Tokens: space.6 = 24px; color.text.default = #1F2933.

RESPONSIVE BEHAVIOUR

Breakpoints: Small from 360 to 767; Medium from 768 to 1199; Large from 1200. Smallest supported width: 360.
Track a parcel, Small (360 to 767 px): D1, D3 at 390
Track a parcel, Medium (768 to 1199 px): Q4
Track a parcel, Large (1200 px and over): D1, D2, D3 at 1280

CONTENT RULES

Tracking number (on D1): rule R1: longest 24; when longer scroll within the field; format letters and digits only.
Carrier note (on D3): rule R2: longest Q5; when longer wrap; format no format stated.
Status label (on D3): no content rule. Q6.

INTERACTIONS

D1 Tracking field: Q7
D2 Track button: I1: Tap Track with a number entered -> The delivery timeline for that number appears.

QUESTIONS FOR THE DESIGN OWNER

Q1 D1 Tracking field: No disabled state is shown in the design or documented for Tracking field. What does it look like, and when does it appear?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q2 D2 Track button: The token space.5 is named for D2 but is not in the token list. Which token or value is meant?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q3 D3 Delivery timeline: No error state is shown in the design or documented for Delivery timeline. What does it look like, and when does it appear?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q4 Track a parcel, Medium: The design shows no layout for Track a parcel between 768 and 1199 px. What should the screen do there?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q5 Carrier note: Content rule R2 gives no longest value for Carrier note. What is the longest value that can occur?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q6 Status label: No content rule exists for Status label. What is the longest value that can occur, and what happens when a value is longer than the design shows?
  Status: Open. Answer: ______ Answered by: ______ Date: ______
Q7 D1 Tracking field: No interaction decision is supplied for D1. What happens when the person uses it?
  Status: Open. Answer: ______ Answered by: ______ Date: ______

SET ASIDE

Inventory row D3 default at 320: the width is below the smallest supported width of 360, so the row takes no part. Is 320 to be supported? If so, the smallest supported width in the settings changes and the record is run again.
Interaction decision I2: it names D9, which is not in the design inventory. Which item is meant?

SIGN-OFF

Design owner: has answered every question and approves this record: ______ Date: ______
Engineer: confirms all 7 questions are resolved and every set-aside line is dealt with: ______ Date: ______

Draft for the design owner. No design has been created or changed, no behaviour has been assumed, and nothing has been sent.
```

## How the figures work out

- Eight inventory rows; the 320 px row is set aside, so seven are used.
- Required states: D1 is a Field with five (default, hover, focus, disabled, error), D2 a Control with six, D3 a Data item with four. That is 15. Covered: D1 four (default and error shown, hover and focus from the library), D2 six, D3 three (default shown, loading and empty from the library). That is 13. Unstated: D1 disabled and D3 error, so 2. 13 plus 2 is 15.
- Breakpoint ranges: Small starts at the smallest supported width, 360, and ends at 767; Medium is 768 to 1199; Large is 1200 and over. Rows at 390 fall in Small and at 1280 in Large; none falls in Medium.
- Seven questions: two states, one token, one breakpoint, two content, one interaction.
