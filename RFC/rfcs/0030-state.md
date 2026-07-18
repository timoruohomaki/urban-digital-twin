---
rfc: 0030
title: State
status: Draft 0.2
category: Core
---

# Abstract

This RFC defines state in the Urban Digital Twin Semantic Framework. State
is the revisable counterpart of the immutable Observation: a State Claim
asserts what is the case for an entity or a configuration of entities, at a
time, within a Semantic Domain — and may be superseded by a better claim.
Observations accumulate; state supersedes. That division is what makes a
digital twin honest about its own currency.

Every Semantic Domain defines its own State Variables, per the Universal
State Principle (RFC0001-P3). A State Claim is made in one of two modes,
estimated from evidence or declared by governance act, and the modes remain
distinguishable. Claims are temporally qualified in two respects — the time
the condition concerns and the time the claim was made — and revision
preserves history: superseded claims remain resolvable.

# Status of This Document

This document is normative. It derives from the principles established in
RFC 0001, uses the terminology of RFC 0002, and builds on the Spatial
Referent (RFC 0010) and Observation (RFC 0040). It resolves the
observation-versus-state boundary left open as Issue RFC0040-I1 and
provides the general state model that Collective State (RFC0080-D3)
specializes. Draft 0.2 adds the triggered path from observation to state
change (Note RFC0030-N6).

# Motivation

The claim that a digital twin is *current* — that it represents the city as
it is, not as it was surveyed — rests entirely on state. An information
system's memory function maintains a representation of the state of its
domain; the twin is, in this respect, the coordinated memory function of
many independently governed domains at once. What the framework must supply
is a shared understanding of what a state claim is, how it relates to the
evidence beneath it, and how it changes — without prescribing any domain's
state model, which the Institutional Autonomy Principle (RFC0001-P5)
forbids.

The observation model of RFC 0040 makes the need concrete. Observations are
immutable events: a thermometer reading is not the temperature of the room,
and a complaint is not the condition of the park (Note RFC0040-N4).
Something else asserts the temperature, the condition, the occupancy — an
assertion that is interpretive, owned by a domain, and revisable when
better evidence or better analysis arrives. That something is the State
Claim. Without it, the twin either freezes evidence into false certainty or
presents raw streams as if they were knowledge.

# Terminology

## Definition

> **Definition RFC0030-D1 — State**
>
> The condition of a State Subject at a time, as interpreted within a
> Semantic Domain and expressed through values of State Variables.

---

> **Definition RFC0030-D2 — State Variable**
>
> A named property, defined by a Semantic Domain, whose values describe an
> aspect of the condition of a State Subject.

---

> **Definition RFC0030-D3 — State Claim**
>
> A revisable, temporally qualified assertion of the value of a State
> Variable for a State Subject, made within a Semantic Domain in a
> distinguishable mode: estimated from evidence, or declared by a
> governance act.

---

> **Definition RFC0030-D4 — State Subject**
>
> The entity, or configuration of entities, that a State Claim concerns.
> Spatial State Subjects are identified through Spatial Referent
> identities.

---

> **Definition RFC0030-D5 — State Transition**
>
> A change in the value of a State Variable for a State Subject, recognized
> from evidence or effected by an Activity, expressed by reference to the
> superseded and the superseding State Claims.

## Scope

This RFC specifies:

- the State Claim and its two modes;
- the relationship between state and observation;
- the temporal qualification of state, including the distinction between
  condition time and claim time;
- revision, supersession and the preservation of claim history;
- State Subjects, including configurations of entities;
- State Transitions and their relationship to evidence and activities.

## Not in Scope

This RFC does not specify:

- the State Variables of any domain, which are domain-owned per
  RFC0001-P3;
- estimation methods and analytics;
- the semantics of Activities that effect transitions (see RFC 0050);
- target or intended states (see Issue RFC0030-I2);
- storage models, versioning schemes and temporal database design.

# Core Concepts

## Observations accumulate; state supersedes

The boundary between observation and state is a boundary of revisability.
An Observation records that an act happened and is never altered
(RFC0040-P3); reinterpretation adds records. A State Claim asserts what is
the case and is *meant* to be superseded: the whole point of a claim about
the present is that a better claim replaces it. This yields an operational
criterion for the boundary left open in Issue RFC0040-I1:

> **Note RFC0030-N1 — The supersession criterion**
>
> If a record is added alongside its predecessors and remains evidence
> forever, it is an Observation — including derived observations such as
> corrected values and computed aggregates. If a record replaces its
> predecessor as the domain's current answer, while the predecessor is
> retained as history, it is a State Claim. A daily average is an
> observation: computing tomorrow's average does not invalidate today's.
> "The spot is currently occupied" is a state claim: the next assertion
> supersedes it.

The same content can appear in both roles, and the parking case
(RFC0040-E5) shows the difference exactly: *at 14:03 the camera estimated
spot 12 occupied* is an immutable Observation; *spot 12 is occupied (as of
14:03, per that series)* is the State Claim a dashboard shows, superseded
minutes later. The observation is what the claim cites; the claim is what
the twin answers with.

## Two modes of claiming

A State Claim is made in one of two modes:

- **Estimated**: the value is produced by analysis of evidence —
  observations in defined roles, prior claims, model outputs. An estimated
  claim should cite its evidence.
- **Declared**: the value is established by a governance act — an asset
  taken out of service by decision, a zoning status entering force, an
  address assigned. A declared claim identifies the act and the Governing
  Authority; its ground is institutional, not evidential.

The modes must remain distinguishable. A consumer treating a declared
status as if it were measured, or an estimate as if it were authoritative
decree, is making exactly the category error the distinction prevents.

> **Note RFC0030-N2 — A recurring pattern**
>
> This is the third appearance of the same design figure in the series:
> asserted versus resolved subject binding (RFC0040-R3), declared versus
> derived Series Scope (RFC0040-R11), and now estimated versus declared
> State Claims. In each case the framework distinguishes what is given by
> an act from what is computed, requires the mode to be distinguishable,
> and refuses to let one silently masquerade as the other. The figure
> follows from the Governance Authority Principle (RFC0001-P4): the
> framework tracks *on what ground* something is said, and leaves the
> judgement of that ground to governance and use.

## Two times

Every State Claim carries two temporal qualifications: the time the
condition concerns (the claim may be about the present, or about a past
period under later analysis) and the time the claim was made. The
distinction is what makes decision histories auditable: evidence-informed
management requires knowing not only what is believed now, but what was
believed when a decision was taken — and revising a state claim must never
quietly rewrite what decision-makers saw at the time.

## Revision preserves history

Supersession is not deletion. A superseded State Claim remains resolvable,
together with its mode, evidence and times, as part of the domain's claim
history. The claim history is itself a source of knowledge: how often a
condition assessment was revised, and in which direction, is information
about both the entity and the observing arrangement.

## State Subjects and configurations

State attaches to a State Subject: a single entity identified by its
Spatial Referent, or a configuration of entities. Configurational state —
introduced for the population domain as Collective State over
Configurations (RFC0080-D5) — is not a population-domain peculiarity: the
level of service of a route, the redundancy of a utility network and the
continuity of a green corridor are all conditions of configurations rather
than of any single referent. RFC 0030 therefore admits configurations as
State Subjects in general; references among the entities of a configuration
are expressed through Spatial Referent identities (consistent with
RFC0080-R6).

> **Note RFC0030-N3 — Collective State as specialization**
>
> Collective State (RFC0080-D3) is a State Claim in the sense of this RFC:
> its State Variables are the population domain's (attributed meaning,
> perceived safety, comfort), its State Subject is a Place or a
> Configuration, its qualification by Membership Criterion is a
> domain-specific claim qualifier, and its estimation from Perception
> Signals is the estimated mode with a defined evidence role. Nothing in
> RFC 0080 requires machinery beyond this RFC; the population domain
> differs in what it claims, not in how claiming works.

## Transitions

A State Transition is the recognition that a State Variable's value has
changed: a new claim supersedes a materially different one. Transitions are
where domains coordinate — a maintenance activity (RFC 0050) effects a
condition transition; a cluster of citizen observations prompts a
recognized one — and they are the natural grain for process description,
where functions are stable and what varies is where state and stakeholders
change. The transition record references the superseded and superseding
claims and, where known, the Activity that effected the change or the
evidence that prompted its recognition.

> **Note RFC0030-N4 — The referent's lifecycle**
>
> Even the existence lifecycle of a Spatial Referent (RFC0010-R5) can be
> read as state under this RFC: the Existence Assertion's standing —
> asserted, withdrawn — is a declared State Claim of the governance domain
> that asserts the referent. This reading adds no obligation to RFC 0010;
> it shows that the framework's own housekeeping needs no second
> mechanism.

> **Note RFC0030-N6 — Observations as triggers**
>
> The link between observation and state runs along two paths. In the
> *recognized* path, evidence accumulates until analysis supersedes a
> claim: the observation changes what is believed. In the *triggered* path,
> an observation sets an Activity in motion — a citizen report opens a
> process, a threshold crossing dispatches an inspection — and the Activity
> effects the transition: the observation changes what is done, and thereby
> what is the case. In process-modeling terms the triggering observation
> enters the function as an arrow: as *input* when it is the material the
> function consumes and transforms, such as a report received and
> classified; as *control* when it conditions whether or how the function
> runs, such as a reading whose threshold crossing activates a response.
> The full treatment of triggers, inputs and controls belongs to RFC 0050.
> This note fixes the semantic point: both paths begin with an Observation
> and end with a superseding State Claim, and everything between them is
> resolvable through the same referent.

# Semantic Relationships

A State Claim:

- **is made within** exactly one Semantic Domain, under its Governing
  Authority;
- **concerns** exactly one State Subject — an entity identified by a
  Spatial Referent, or a configuration of such entities;
- **assigns a value to** exactly one State Variable;
- **is qualified by** condition time and claim time, and by domain-specific
  qualifiers such as a Membership Criterion (RFC0080-D2);
- **is made in** the estimated or the declared mode;
- **may cite** Observations, prior State Claims and model outputs as
  evidence (estimated mode) or **identifies** a governance act (declared
  mode);
- **may be superseded by** a later State Claim, remaining resolvable as
  history.

A State Transition **references** a superseded and a superseding State
Claim, and **may reference** the Activity (RFC 0050) that effected it or
the evidence that prompted its recognition. An Activity, in turn, **may be
triggered by** Observations, which enter it as inputs or controls in the
process-modeling sense (Note RFC0030-N6).

# Design Principles

## Principle RFC0030-P1 — Supersession Principle

> A State Claim **shall** be revisable by supersession. Supersession
> **shall not** erase: superseded claims remain resolvable as history.

## Principle RFC0030-P2 — Grounded Claims Principle

> Every State Claim **shall** be made in a distinguishable mode — estimated
> from evidence or declared by governance act — and **shall** carry the
> ground appropriate to its mode.

# Normative Requirements

> **Requirement RFC0030-R1 — Domain state models**
>
> Every Semantic Domain shall define the State Variables applicable to the
> State Subjects within its scope. No domain's state model shall be
> required to conform to another's.

---

> **Requirement RFC0030-R2 — Claim content**
>
> A State Claim shall reference its Semantic Domain, its State Subject, its
> State Variable and its value, and shall be qualified by both the time the
> condition concerns and the time of the claim.

---

> **Requirement RFC0030-R3 — Claim mode and ground**
>
> A State Claim shall record its mode. An estimated claim should cite its
> evidence; a declared claim shall identify the governance act and the
> Governing Authority establishing it.

---

> **Requirement RFC0030-R4 — Supersession with history**
>
> Revision of state shall be expressed by superseding claims. A superseded
> State Claim, with its mode, ground and temporal qualifications, shall
> remain resolvable.

---

> **Requirement RFC0030-R5 — Configurational subjects**
>
> A State Subject may be a configuration of entities. A configurational
> subject shall reference its member entities, and the relationships among
> them, through Spatial Referent identities.

---

> **Requirement RFC0030-R6 — Transitions**
>
> A State Transition shall reference the superseded and superseding State
> Claims, and should reference the Activity that effected the change or
> the evidence that prompted its recognition.

# Examples

> **Example RFC0030-E1 — Occupancy: stream to state**
>
> The parking camera of RFC0040-E5 produces immutable occupancy
> Observations per spot. The parking domain maintains, per spot referent, a
> State Claim in the estimated mode: *occupied as of the latest reliable
> observation*, citing the Series and inheriting its quality context.
> Claims supersede one another minute by minute; the Observations
> accumulate untouched. When the camera's Quality Statement fails
> conformance, the claims' evidential ground is visibly weakened without a
> single Observation changing — precisely the separation the two concepts
> exist to provide.

---

> **Example RFC0030-E2 — A bench in two modes**
>
> A park bench carries two condition-related State Claims. The first is
> estimated: condition grade *poor*, claimed by the asset domain's
> assessment process, citing an inspection observation and three citizen
> reports in the Perception Signal role. The second is declared: status
> *taken out of service*, established by a maintenance decision — a
> governance act with a date and an authority, requiring no evidence. When
> repair work (an Activity, RFC 0050) completes, a transition supersedes
> both: condition *good*, estimated from the post-repair inspection, and
> status *in service*, declared by the work's acceptance. The claim history
> retains the whole sequence, and a later audit can see what was believed,
> on what ground, at every point.

---

> **Example RFC0030-E3 — Level of service of a route**
>
> The school route of RFC0080-E3 is a configuration of street segments and
> crossings. The mobility domain claims a level-of-service state for the
> configuration — estimated from crossing observations, maintenance states
> of the member segments and seasonal factors. The claim concerns the
> configuration as such: no single referent bears it, and its value is not
> an average of member states. Collective State claims about the same
> configuration by the population domain (perceived safety among
> caregivers) coexist orthogonally, per RFC0001-P2.

# Planned Figures

> **Figure RFC0030-F1 (placeholder)**
>
> Observations accumulate, state supersedes: the evidence layer feeding
> revisable State Claims, with claim history preserved.
>
> *[Diagram to be inserted: fig-rfc0030-f1-observation-vs-state.svg]*

---

> **Figure RFC0030-F2 (placeholder)**
>
> The two modes and two times of a State Claim: estimated versus declared
> ground; condition time versus claim time.
>
> *[Diagram to be inserted: fig-rfc0030-f2-modes-and-times.svg]*

---

> **Figure RFC0030-F3 (placeholder)**
>
> A State Transition referencing superseded and superseding claims, with an
> effecting Activity and prompting evidence.
>
> *[Diagram to be inserted: fig-rfc0030-f3-transition.svg]*

# Standards and Implementation Mappings

The following correspondences are informative.

| Framework concept | Correspondence (informative) |
|---|---|
| State (memory function) | Olivé's memory function of an information system: maintaining a representation of the state of a domain |
| State Variable | ISO 55000 asset condition and criticality; domain code lists and registries |
| State Claim, estimated | "Current view" tables and dashboards derived from observation streams |
| State Claim, declared | Registry entries established by administrative decision; statutory statuses |
| Two times | Bitemporal data management: valid time and transaction time |
| Supersession with history | Temporal tables; slowly changing dimensions in dimensional models |
| State Transition | Status and process events, e.g. civic-report ticket status changes feeding `process_events`-style fact tables |

> **Note RFC0030-N5 — Where SensorThings stops**
>
> The SensorThings API deliberately models observations, not state: it has
> no entity for "the current condition." Implementations that surface a
> latest-value view are constructing estimated State Claims from a
> Datastream — usually silently. This RFC makes that construction explicit
> and gives it its obligations: mode, ground, two times, and history.

# Open Questions

> **Issue RFC0030-I1 — Common state variable patterns**
>
> Condition, availability and occupancy recur across domains. Should the
> framework define informative patterns for such variables to ease
> cross-domain reading, or would even informative patterns erode domain
> autonomy (RFC0001-P5)?

---

> **Issue RFC0030-I2 — Intended state** *(resolved by RFC 0050)*
>
> Targets — an SLA response time, a setpoint, a planned condition grade —
> are not claims about what is the case but constraints on what should be.
> Resolved: RFC 0050 defines Intended State as a Control (RFC0050-D6,
> RFC0050-R5). A target has different truth conditions than a State Claim —
> it becomes unmet, not false — and its comparison against actual state is
> analysis producing ordinary evidence and claims under RFC 0040 and this
> RFC.

---

> **Issue RFC0030-I3 — Quality Statements as state of the observer**
>
> A Quality Statement scoped to an Observer with a validity period
> (RFC0040-R7) behaves like a State Claim about the observing arrangement.
> Whether to unify the two concepts or keep the quality model as a
> deliberately specialized parallel is open; unification would simplify the
> ontology at the cost of coupling RFC 0040 to this RFC.

---

> **Issue RFC0030-I4 — Ownership of the configuration concept**
>
> RFC 0080 defines Configuration for Places (RFC0080-D5); this RFC admits
> configurations for State Subjects in general. Whether the general
> concept should be defined here (or in RFC 0010) with RFC 0080
> specializing it — and the definitions reconciled accordingly — is open.

# References

- RFC 0000 — Introduction
- RFC 0001 — Design Principles
- RFC 0002 — Terminology and Naming Conventions
- RFC 0010 — Spatial Referent
- RFC 0040 — Observation
- RFC 0050 — Activity (planned)
- RFC 0080 — Population
- Editorial Style Guide
- A. Olivé, *Conceptual Modeling of Information Systems*. Berlin:
  Springer, 2010. (informative)
- ISO, "ISO 55000:2014 Asset Management — Overview, Principles and
  Terminology," revised series 2024. (informative)
- Open Geospatial Consortium, "OGC SensorThings API Part 1: Sensing," OGC
  document 15-078r6, 2016. (informative)
