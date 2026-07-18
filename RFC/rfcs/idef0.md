# IDEF0

Status: Draft. Non-normative.

This mapping relates IDEF0 functional modeling (IEEE 1320.1) to the
concepts of the Urban Digital Twin Semantic Framework, principally RFC 0050
(Activity), with connections to RFC 0030 (State) and RFC 0040
(Observation). IDEF0 models what functions do, not the attributes of the
objects passing through them; its arrows represent constraints and
dependencies, not data structures (RFC0050-P2).

## Element mapping

| IDEF0 element | Framework concept | Notes |
|---|---|---|
| Function | Activity (RFC0050-D1) | Stable structure; variation carried by arrows (RFC0050-P1) |
| Input arrow | Consumed inputs, including triggering Observations in the input role (RFC0050-D3, Note RFC0030-N6) | What the function consumes and transforms |
| Control arrow | Control (RFC0050-D4), including Intended State (RFC0050-D6) and threshold-type Observations in the control role | Absence of a control is meaningful (RFC0050-R3) |
| Output arrow | Produced outputs, including Observations (RFC 0040) and effected State Transitions (RFC0030-D5) | State changes are expressed as transitions referencing the Activity (RFC0050-R4) |
| Mechanism arrow | Mechanism (RFC0050-D5) | Organizations, units, systems, persons in roles |
| Decomposition | Activity decomposition (RFC0050-R6) | External arrows preserved |

## Principles preserved from IDEF0 practice

- Function structures are stable while arrows vary: one
  receive–classify–act–resolve structure serves a service taxonomy of
  hundreds of types; what differs per type is which controls apply, which
  mechanisms perform, and what flows through (RFC0050-P1).
- The presence or absence of a control arrow determines whether a control
  path applies at all — an undefined SLA is not a zero-valued SLA
  (RFC0050-R3, Note RFC0050-N2).
- An arriving artefact means capability, not data structure: a photo as
  input means "visual evidence exists, changing what downstream functions
  can do," not "a file with metadata" (Note RFC0050-N1).
- State transitions concentrate at function boundaries: where state and
  stakeholder responsibility change is where domains coordinate
  (RFC0050-R6; RFC 0030, Transitions).
- Acts that both observe and act need no special construct: a function
  with an Observation among its outputs and a State Transition among its
  effects (RFC 0050, resolution of Issue RFC0040-I3).

## Notable divergences

- IDEF0 is a modeling notation with graphical syntax; the framework
  borrows its functional decomposition semantics without adopting the
  notation as normative. Machine-readable IDEF0 models (for example those
  exported by desktop modeling tools) are an implementation binding for
  Process descriptions, not their definition.
- IDEF0 does not distinguish evidence from state among the things arrows
  carry; the framework does (RFC 0030, RFC 0040), and the mapping above
  assigns each arrow role its framework counterpart accordingly.
