---
rfc: 0050
title: Activity
status: Draft 0.1
category: Core
---

# Abstract

This RFC defines the activity concepts of the Urban Digital Twin Semantic
Framework. An Activity is a temporally qualified act or function, performed
by Mechanisms under Controls, that consumes inputs and produces outputs —
and through which state changes are effected. A Process is an arrangement of
Activities through which a Governing Authority manages State Subjects, with
state and stakeholder responsibility changing at Activity boundaries.

The model is function-centric: Activity structures are stable, and variation
across cases is carried by the arrows — inputs, controls, outputs and
mechanisms — rather than by a proliferation of functions. Intended State
enters the framework here, as a Control: a target asserts what should be the
case and conditions execution; it is not a claim about what is. This RFC
resolves the placement of intended state (Issue RFC0030-I2) and the
treatment of acts that both observe and act (Issue RFC0040-I3).

# Status of This Document

This document is normative. It derives from the principles established in
RFC 0001, uses the terminology of RFC 0002, and builds on the Spatial
Referent (RFC 0010), State (RFC 0030) and Observation (RFC 0040). The
non-normative process-modeling mapping is maintained in `mappings/idef0.md`.

# Motivation

A twin that models geometry, observations and state can say what the city
is, but not what is being done about it. Yet the doing is where the
evidence loop closes: a citizen observation triggers a process, the process
effects a state transition, the new state is observed again. Without an
activity model, the middle of that loop is invisible — locked inside
workflow systems as implementation, absent from the semantic level where
domains coordinate.

The framework's activity model is function-centric by deliberate choice. An
object-centric process description must multiply with the variety of things
processed; a function-centric one remains stable while the variety flows
through its arrows. The empirical case is strong: a five-year civic
reporting corpus with a taxonomy of 184 service types exhibits one function
structure — receive, classify, act, resolve — for all of them. What varies
per type is which controls apply, which mechanisms perform the work, and
what flows in and out. Modeling 184 processes would be a category error;
modeling one function structure with varying arrows is the truth of the
matter.

# Terminology

## Definition

> **Definition RFC0050-D1 — Activity**
>
> A temporally qualified act or function, performed by one or more
> Mechanisms under applicable Controls, that consumes inputs and produces
> outputs, and through which State Transitions are effected.

---

> **Definition RFC0050-D2 — Process**
>
> An arrangement of Activities with defined boundaries, through which a
> Governing Authority manages State Subjects. State and stakeholder
> responsibility change at Activity boundaries.

---

> **Definition RFC0050-D3 — Trigger**
>
> The occurrence that initiates an Activity: an Observation, a State
> Transition, a governance act or a schedule.

---

> **Definition RFC0050-D4 — Control**
>
> A constraint that conditions whether or how an Activity executes, such as
> a policy, a statutory requirement, a threshold or an Intended State.

---

> **Definition RFC0050-D5 — Mechanism**
>
> The arrangement that performs an Activity: an organization, an
> organizational unit, a system, or a person acting in a role.

---

> **Definition RFC0050-D6 — Intended State**
>
> A target value of a State Variable, expressed as a Control. An Intended
> State asserts what should be the case for a State Subject; it is not a
> State Claim.

## Scope

This RFC specifies:

- the Activity and its arrows: inputs, Controls, outputs, Mechanisms;
- the Process as an arrangement of Activities;
- Triggers, including Observations in input and control roles;
- Intended State as a Control;
- the relationships between Activities, State Transitions and
  Observations.

## Not in Scope

This RFC does not specify:

- workflow execution, scheduling and resourcing;
- organizational structures and mandates, which belong to RFC 0060;
- specific process notations or their exchange formats;
- performance and compliance analytics, which are estimation over
  activity records per RFC 0030 and RFC 0040;
- the domain-specific content of any process.

# Core Concepts

## Functions are stable; arrows vary

The unit of process description is the function — the Activity — not the
case flowing through it. Cases vary without limit: service types, asset
classes, seasons, severities. Functions do not: the structure that
receives, classifies, acts and resolves is the same whether the subject is
a pothole or a fallen tree. The framework therefore requires that variation
be expressed in the arrows. A new service type is a new combination of
controls, mechanisms and flows over the same functions — not a new process.

> **Note RFC0050-N1 — Arrows are dependencies, not data structures**
>
> An input arrow asserts that the function consumes and transforms
> something; a control arrow asserts that something conditions execution.
> Neither is a schema. A photo arriving as input means *visual evidence
> exists, which changes what downstream functions can do* — not *a file
> with metadata*. The semantic content of an arrow is the dependency it
> creates, and modeling it as a data structure both overcommits (to a
> format) and undercommits (missing the dependency).

## Triggers: observations as input or as control

Per Note RFC0030-N6, an Observation may initiate an Activity in two roles.
As *input*, the observation is the material the function consumes — a
report received and classified. As *control*, the observation conditions
execution — a reading whose threshold crossing activates a response
function that consumes other inputs entirely. The roles must remain
distinguishable; they are another instance of the recurring figure named in
Note RFC0030-N2, the framework tracking on what ground something
participates. Triggers beyond observations — a State Transition entering a
condition that mandates action, a governance act, a schedule — initiate on
institutional rather than evidential ground.

## Intended State is a Control

A target — an SLA response time, a setpoint, a planned condition grade —
has different truth conditions than a State Claim: it does not become false
when reality disagrees, it becomes *unmet*. It is established by policy
rather than superseded by evidence, and its semantic job is to condition
activities: to determine which response path applies and when escalation
fires. The framework therefore places Intended State among Controls,
resolving Issue RFC0030-I2. The comparison of intended against actual state
is analysis: it produces evidence and claims about performance — an on-time
ratio, a compliance state — under the ordinary machinery of RFC 0040 and
RFC 0030, not a new construct.

> **Note RFC0050-N2 — Absent controls**
>
> The absence of a Control is meaningful and must not be conflated with a
> permissive value. A service type with no SLA defined is not a service
> type with an infinite SLA: no escalation path applies, no compliance
> measure is computable, and a performance analysis must report *not
> defined* rather than *always met*. In a profiled civic reporting corpus,
> roughly one type in seven carried no SLA — a fact about the governance of
> those types, visible only if absence is representable.

## Acts that observe and act

An inspection during maintenance both records a condition and changes the
world. No special construct is needed: it is an Activity that produces an
Observation among its outputs and effects a State Transition among its
effects. The factoring rule of Note RFC0040-N3 generalizes: acts are
Activities; what they record is Observations; what they change is State
Transitions. This resolves Issue RFC0040-I3.

> **Note RFC0050-N3 — The ISO 55000 event model**
>
> The asset management reading of this RFC follows the ISO 55000 event
> model: stakeholders interact with assets, events occur, and processes
> are sequences of events through which the asset lifecycle is managed. In
> framework terms, stakeholders appear as Mechanisms (performing) and as
> Observers (perceiving, per RFC 0040); events appear as Activities and
> the State Transitions they effect; and the lifecycle process is a
> Process over State Subjects identified by Spatial Referents. The civic
> engagement chain — a stakeholder identifies an issue, which triggers a
> process, which is a sequence of events — is this model verbatim, with
> the identifying stakeholder as an Observer whose Observation is the
> Trigger.

## Processes and their boundaries

A Process arranges Activities under one Governing Authority's
responsibility. Its boundaries are semantic, not administrative
conveniences: an Activity boundary is where state changes and where
stakeholder responsibility passes — the points at which other domains can
meaningfully attach. A Process is decomposable: an Activity may be refined
into a finer arrangement of Activities without changing its external
arrows, in the manner of hierarchical function decomposition.

# Semantic Relationships

An Activity:

- **is performed by** one or more Mechanisms;
- **is conditioned by** zero or more Controls, including Intended States;
  the absence of a Control is representable as absence;
- **may be initiated by** a Trigger; a triggering Observation participates
  as input or as control, distinguishably;
- **concerns** State Subjects, referenced through Spatial Referent
  identities;
- **consumes** inputs and **produces** outputs, including Observations
  (RFC 0040);
- **effects** State Transitions (RFC0030-D5), which reference it;
- **belongs to** zero or more Processes and **may decompose into** finer
  Activities.

A Process **is governed by** exactly one Governing Authority and
**arranges** Activities with defined boundaries. An Intended State
**targets** a State Variable of a State Subject and **conditions**
Activities as a Control.

# Design Principles

## Principle RFC0050-P1 — Function Stability Principle

> Variation across cases **shall** be expressed through inputs, Controls,
> outputs and Mechanisms. New case varieties **shall not** require new
> Activity structures where the function performed is the same.

## Principle RFC0050-P2 — Arrow Dependency Principle

> Inputs, Controls, outputs and Mechanisms express dependencies and
> constraints. They **shall not** be specified as data structures at the
> semantic level.

# Normative Requirements

> **Requirement RFC0050-R1 — Activity content**
>
> An Activity shall reference its performing Mechanisms, its temporal
> extent, and the State Subjects it concerns through Spatial Referent
> identities.

---

> **Requirement RFC0050-R2 — Trigger provenance**
>
> An Activity should record its Trigger. A triggering Observation shall be
> referenced by identity, and its role — input or control — shall be
> distinguishable.

---

> **Requirement RFC0050-R3 — Controls and their absence**
>
> The Controls applicable to an Activity shall be identifiable. The absence
> of a Control shall be distinguishable from a Control with a permissive
> value.

---

> **Requirement RFC0050-R4 — Effects as transitions**
>
> State changes effected by an Activity shall be expressed as State
> Transitions referencing the Activity, per RFC0030-R6. Observations
> produced by an Activity are Observations in the full sense of RFC 0040,
> with the performing Mechanism identifiable in the Observer provenance.

---

> **Requirement RFC0050-R5 — Intended State as Control**
>
> An Intended State shall be expressed as a Control and shall not be
> expressed as a State Claim. Assessment of actual state against an
> Intended State shall be treated as analysis, producing Observations or
> State Claims under RFC 0040 and RFC 0030.

---

> **Requirement RFC0050-R6 — Process boundaries**
>
> A Process shall define its Activity boundaries such that State
> Transitions and changes of stakeholder responsibility occur at
> boundaries. Decomposition of an Activity shall preserve its external
> inputs, Controls, outputs and Mechanisms.

# Examples

> **Example RFC0050-E1 — The bench, as process**
>
> The bench of Example RFC0030-E2, seen from the activity side. A citizen's
> report — an Observation in the Perception Signal role — triggers the
> maintenance process as input. Receive and classify run under a
> classification scheme as Control; for this asset class an SLA defines a
> response-time Intended State, so an escalation path applies. The repair
> Activity is performed by a works unit as Mechanism, consumes the work
> order, produces a post-repair inspection Observation among its outputs,
> and effects the two transitions of RFC0030-E2 — condition to *good*,
> status to *in service*. A neighbouring asset class carries no SLA: for
> its tickets no escalation path exists and compliance is *not defined*,
> visibly, per RFC0050-R3.

---

> **Example RFC0050-E2 — Threshold as control**
>
> A water-level sensor observes a culvert. Its Series feeds no process in
> normal conditions. A response function is conditioned by a threshold
> Control: when a reading crosses it, the inspection Activity initiates —
> the observation acting as control, not as input, since the inspection
> consumes crew time and site access, not the reading itself. The
> inspection is a mixed act resolved per this RFC: it produces a condition
> Observation and, if damage is found, effects a status transition that
> triggers the repair process in turn — a Trigger of the State Transition
> kind.

---

> **Example RFC0050-E3 — Mandated participation as process**
>
> A zoning consultation is a Process under statutory Controls: a
> participation requirement and a response deadline. Citizen responses are
> Observations anchored to the planning zone's Spatial Referent, entering
> the consultation Activity as inputs. The Mechanism is the planning
> authority; the outputs include a consultation summary — a derived
> Observation — and the effect is a declared State Transition: the plan's
> status advances by governance act. A legal obligation becomes a
> structured part of the twin without any machinery beyond this RFC series.

# Planned Figures

> **Figure RFC0050-F1 (placeholder)**
>
> The Activity and its arrows: inputs, Controls (including Intended State),
> outputs (including Observations), Mechanisms, and effected State
> Transitions.
>
> *[Diagram to be inserted: fig-rfc0050-f1-activity-arrows.svg]*

---

> **Figure RFC0050-F2 (placeholder)**
>
> One function structure, varying arrows: the receive–classify–act–resolve
> structure with per-type Controls and Mechanisms.
>
> *[Diagram to be inserted: fig-rfc0050-f2-function-stability.svg]*

---

> **Figure RFC0050-F3 (placeholder)**
>
> The closed evidence loop: Observation triggers Activity; Activity effects
> State Transition; new state is observed again — all joined on one
> Spatial Referent.
>
> *[Diagram to be inserted: fig-rfc0050-f3-evidence-loop.svg]*

# Standards and Implementation Mappings

The following correspondences are informative. The process-modeling mapping
is elaborated in `mappings/idef0.md`.

| Framework concept | Correspondence (informative) |
|---|---|
| Activity | IDEF0 function; W3C PROV `prov:Activity` |
| Mechanism | IDEF0 mechanism arrow; W3C PROV `prov:Agent` |
| Input / output | IDEF0 input and output arrows; PROV `used` / `generated` |
| Control | IDEF0 control arrow; SLA definitions in civic reporting service definitions |
| Intended State | SLA targets; setpoints in control systems; planned condition grades in asset management |
| Process | ISO 55000 lifecycle processes; civic reporting workflow (receive, classify, act, resolve) |
| Trigger | Civic report submission; threshold rules; statutory initiation |
| Effects as transitions | Ticket status change events feeding `process_events`-style fact tables (RFC 0030 mappings) |

# Open Questions

> **Issue RFC0050-I1 — Events versus Activities**
>
> Is an atomic status-change record an Activity, or only the trace of one?
> The current lean: records are outputs and transitions; Activities are the
> functions that produce them. A degenerate Activity with instantaneous
> extent may still be admitted for acts with no meaningful duration.

---

> **Issue RFC0050-I2 — Cross-authority processes** *(resolved by RFC 0060)*
>
> A process spanning Governing Authorities — a utility's repair inside a
> city's street works — requires handoff semantics. Resolved: RFC0060-R7 —
> responsibility passes through a Governance Act of acceptance at an
> Activity boundary, the Controls of the responsible authority apply within
> each segment, and the State Subjects' referent identities persist across
> the handoff. Procedural detail remains institutional.

---

> **Issue RFC0050-I3 — Planned Activities**
>
> A maintenance plan names future Activities. Whether a planned Activity is
> an Activity with future temporal extent, a Control on present ones, or a
> distinct construct is open; the answer interacts with Intended State.

---

> **Issue RFC0050-I4 — Resources**
>
> Activities consume resources — budget, crew time, materials — and
> resource constraints behave partly like Controls. Whether the framework
> should name a resource concept (echoing the third element of Turner's
> triad) or leave it domain-owned is open.

# References

- RFC 0000 — Introduction
- RFC 0001 — Design Principles
- RFC 0002 — Terminology and Naming Conventions
- RFC 0010 — Spatial Referent
- RFC 0030 — State
- RFC 0040 — Observation
- RFC 0060 — Governance and Authority (planned)
- Editorial Style Guide
- `mappings/idef0.md` — process-modeling mapping (non-normative)
- IEEE, "IEEE Standard for Functional Modeling Language — Syntax and
  Semantics for IDEF0," IEEE 1320.1-1998. (informative)
- ISO, "ISO 55000:2014 Asset Management — Overview, Principles and
  Terminology," revised series 2024. (informative)
- W3C, "PROV-O: The PROV Ontology," W3C Recommendation, 2013.
  (informative)
- Open311, "A Collaborative Model and Open Standard for Civic Issue
  Tracking." (informative)
