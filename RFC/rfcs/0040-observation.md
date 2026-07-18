---
rfc: 0040
title: Observation
status: Draft 0.4
category: Core
---

# Abstract

This RFC defines the observation concepts of the Urban Digital Twin Semantic
Framework. An Observation is a temporally qualified act in which an Observer
produces a Result estimating an Observed Property of a Subject. The framework
adopts one observation model for all observers: instruments, humans and
computational processes observe on equal semantic terms.

Three spatial facts are distinguished throughout: the location of the
Observer, the Series Scope an Observation Series covers, and the identity of
the Subject each observation is about. The normative commitment of this RFC
is subject binding — every observation about a spatial entity binds its
Subject to a Spatial Referent (RFC 0010) — while the observer's own location
is provenance and the Series Scope serves discovery. Observations are immutable events:
they are evidence from which state claims are made, and reinterpretation
produces new records, never rewrites.

Quality is part of the model. Quality Statements — produced by Quality
Evaluations and scoped to a Result, an Observer or a Series — are resolvable
from the observations they qualify, so that a stream is self-explanatory:
live processing can compensate, filter or weight without out-of-band
knowledge. Correction is derivation; originals never change.

# Status of This Document

This document is normative. It derives from the principles established in
RFC 0001, uses the terminology of RFC 0002, and builds on the Spatial
Referent defined in RFC 0010. RFC 0080 consumes the concepts defined here
through the Perception Signal role (RFC0080-D4). Draft 0.2 adds the data
quality model (RFC0040-D7 to RFC0040-D9, RFC0040-R7 to RFC0040-R10),
building on groundwork laid in an earlier sensor data quality implementation
based on ISO 19157. Draft 0.3 adds the Series Scope (RFC0040-D10,
RFC0040-R11). Draft 0.4 resolves the qualitative results question
(RFC0040-I2, Note RFC0040-N8).

# Motivation

Urban Digital Twins are fed by heterogeneous acts of observation: fixed
sensors reporting air quality, mobile platforms measuring as they move,
citizens reporting a broken bench or an unsafe corner, computational
processes deriving indicators from imagery or text. Existing practice models
these separately — sensor data through IoT standards, citizen input through
service request systems, derived data through analytics pipelines — and the
separation carries an implicit hierarchy in which instrument data is "real"
telemetry and human input is something softer.

The framework rejects that hierarchy. A citizen reporting on the condition
of a place is an observer estimating a property of a subject, exactly as a
sensor is; what differs is the observed property and the provenance, not the
semantic structure. Treating human perception, crowdsourcing and citizen
science on the same terms as instrument observation is a stated design
objective of the socio-technical Urban Digital Twin, and it requires exactly
one thing of the semantic model: a single observation concept broad enough
for all observers, with assessment of evidential weight left out of the
semantics (Note RFC0080-N9).

A second motivation is locational precision. Observation infrastructures
routinely conflate where the observing equipment is with what the
observation is about. A gateway serves thousands of lamp posts; a camera
watches an area it does not occupy; a citizen stands somewhere other than
the pothole they report. The model must therefore distinguish observer
location from observation subject, and must state how a subject expressed
as a position resolves to an identified entity.

# Terminology

## Definition

> **Definition RFC0040-D1 — Observation**
>
> A temporally qualified act in which an Observer produces a Result
> estimating an Observed Property of a Subject.

---

> **Definition RFC0040-D2 — Observer**
>
> The agent or arrangement that performs Observations. An Observer may be an
> instrument, a human, or a computational process.

---

> **Definition RFC0040-D3 — Observed Property**
>
> The property of the Subject that an Observation estimates.

---

> **Definition RFC0040-D4 — Result**
>
> The value produced by an Observation, together with any qualification of
> that value. A Result may be quantitative or qualitative, including free
> text.

---

> **Definition RFC0040-D5 — Subject**
>
> The entity an Observation is about. When the Subject is spatial, it is
> identified by a Spatial Referent.

---

> **Definition RFC0040-D6 — Observation Series**
>
> An ordered collection of Observations sharing an Observer, an Observed
> Property and a Subject or subject pattern.

---

> **Definition RFC0040-D7 — Quality Statement**
>
> A statement qualifying the reliability of a Result, an Observer or an
> Observation Series, produced by a Quality Evaluation and recorded together
> with the method and time of its production.

---

> **Definition RFC0040-D8 — Quality Evaluation**
>
> An act that produces a Quality Statement by a stated method. A Quality
> Evaluation is itself an Observation whose Subject is the Result, Observer
> or Observation Series evaluated.

---

> **Definition RFC0040-D9 — Correction**
>
> A derivation that produces new Observations or Observation Series by
> applying a stated correction function to existing ones. The originals are
> retained unaltered.

---

> **Definition RFC0040-D10 — Series Scope**
>
> The spatial extent within which an Observation Series finds its Subjects.
> A Series Scope may be declared in advance or derived from the Subjects
> observed.

## Scope

This RFC specifies:

- the common observation model for instrument, human and computational
  observers;
- the distinction between Observer location and Subject;
- the binding of spatial Subjects to Spatial Referents, including
  resolution from position to identity;
- the immutability of Observations and their role as evidence;
- the organization of Observations into Series;
- the spatial scope of an Observation Series;
- data quality: Quality Statements, their scopes, and their production by
  Quality Evaluations;
- Correction as derivation.

## Not in Scope

This RFC does not specify:

- assessment of evidential weight, representativeness or quality (Note
  RFC0080-N9);
- state and state estimation, which belong to RFC 0030 and RFC 0080;
- the processes that observations may trigger, which belong to RFC 0050;
- calibration and sensor management procedures, beyond the Quality
  Statements they produce;
- thresholds of fitness for use, which belong to consuming use cases;
- the analysis and interpretation of Results, quantitative or qualitative;
- encodings, APIs and transport.

# Core Concepts

## One model, many observers

The framework defines a single observation concept. An air quality sensor,
a citizen submitting a georeferenced report and a language model deriving a
sentiment indicator from free text are all Observers producing Results about
Observed Properties of Subjects. Their differences — calibration,
subjectivity, method — are provenance to be recorded, not semantic
distinctions to be modeled as separate kinds.

> **Note RFC0040-N1 — Subjectivity is not a defect**
>
> A perception observation estimates an experiential property — perceived
> safety rather than luminance. The property differs; the observation
> structure does not. Whether a given observation is good evidence for a
> given claim is a matter for the governance under which the claim is made,
> per Note RFC0080-N9. The semantic model's task is to position the
> observation, not to grade it.

> **Note RFC0040-N8 — Qualitative results as payload, context as support**
>
> A qualitative Result is payload in the same sense that a quantitative
> Result is: the framework defines the vehicle of collection and its
> position, not the analysis. What a unit reference does for a number —
> making it interpretable by binding it to an externally governed system
> such as the SI — the Observed Property's vocabulary binding (RFC0040-R5)
> and the observation's positioning do for text. The ways of analysing
> either kind of Result are out of scope. Where the framework does support
> qualitative analysis is in the context it makes resolvable from any
> single observation: through the Subject's referent, an analyst reaches
> the conditions surrounding the actor and the place — the state claims of
> other domains, the structural demographics of the containing area,
> concurrent Observation Series and earlier surveys over the same scope,
> and the quality of all of it. The framework situates the free text; what
> is read out of it is a use-case matter, per the assessment boundary of
> Note RFC0040-N6.

## Observer location and Subject

Every observation involves two potentially distinct spatial facts: where
the Observer is, and what the observation is about. Three recurring
patterns cover urban observation practice:

1. **Observer-located**: the observation concerns the place where the
   Observer is — a fixed in-situ sensor.
2. **Trace-located**: the Observer moves, and each Observation is qualified
   by the Observer's position at observation time — a measurement vehicle,
   a sensor on a bus.
3. **Subject-located**: the observation concerns a Subject distinct from
   the Observer's location — a camera watching an area, a gateway serving
   many devices, a citizen reporting on a place they observed.

In all three patterns the normative element is the same: the Subject binds
to a Spatial Referent. The Observer's location is provenance — indispensable
for interpretation and for resolution, but never a substitute for subject
identity.

Between the Observer's location and the individual Subject lies a third
spatial fact: the extent an Observation Series covers. A camera mounted to
monitor a parking area has a location (its mount), a coverage (its field of
view — the total area under surveillance), and, per Observation, a Subject
(a single parking spot). The framework names this intermediate extent the
Series Scope (RFC0040-D10). A Series Scope may be declared in advance — a
configured field of view, a patrol corridor — or derived from the Subjects
actually observed, and the two modes must remain distinguishable, in
parallel with subject binding (RFC0040-R3). The scope's principal service
is discovery: it answers which Series observe a given referent or area
without enumerating every Observation.

> **Note RFC0040-N2 — Correspondence to OGC SensorThings**
>
> The concepts correspond to the ways the OGC SensorThings API references
> location — four, at different levels of its entity model: the `Location`
> of a Thing (observer-located), its `HistoricalLocations` (trace-located),
> the `observedArea` of a Datastream (the Series Scope), and the
> `FeatureOfInterest` of an Observation (subject-located). SensorThings'
> separation of the Thing from its FeatureOfInterest is the
> implementation-level precedent for this RFC's separation of Observer from
> Subject — a public lighting system may expose one gateway as the Thing
> while each lamp post, or the area a single lamp illuminates, is the
> feature of interest — and its `observedArea` is the precedent for the
> Series Scope. The framework generalizes these precedents beyond
> instrument observation.

## From position to identity

Observations frequently arrive carrying only a position — coordinates
supplied by a device or a reporting citizen. A position is not a Subject.
The binding of an observation to a Spatial Referent occurs in one of two
modes:

- **Asserted**: the Observer identifies the Subject directly — a citizen
  selects the specific asset being reported, or a datastream is configured
  against a known referent.
- **Resolved**: the Subject is determined by spatial resolution of the
  observed position against Anchor Geometries (RFC0010-D4) — nearest
  feature, containing feature — under rules owned by the resolving
  authority.

The two modes differ in provenance and must remain distinguishable: an
asserted binding is part of the observation act; a resolved binding is an
interpretation added to it, and may be revised as resolution improves
without altering the observation itself.

## Observations are immutable evidence

An Observation records that an act happened: this observer produced this
result about this subject at this time. That record does not change.
Corrections, recalibrations, improved resolutions and reinterpretations are
new records that reference the original. This is what makes observations
usable as evidence: a Collective State claim (RFC0080-D3) or an asset
condition assessment can cite observations knowing the citations will not
drift. State is interpretation and may be revised at any time; observations
are the fixed points revision works from.

## Quality as self-explanatory provenance

Data quality enters the model as observation semantics, not as an
afterthought of storage. A Quality Statement qualifies the reliability of a
Result, an Observer or a Series, and is produced by a Quality Evaluation —
an act that is itself an Observation whose Subject is the thing evaluated.
The scopes reflect where quality actually resides: accuracy, repeatability
and stability are properties of an observing arrangement, established at
evaluation time and valid for a period; conformance is an evaluation of
results against a named specification; the qualification of a single Result
is the narrowest case. Because Quality Statements are positioned in the
model and resolvable from the observations they qualify, a stream carries
what its consumers need in order to interpret it: it is self-explanatory,
and live processing can compensate, filter or weight without out-of-band
knowledge.

Correction closes the loop. Where an evaluation yields a compensation
function, a Correction applies it, producing derived Observations or Series
that reference their originals and the function applied. Under the
Observation Immutability Principle the originals never change; the corrected
stream exists alongside them with its derivation declared.

> **Note RFC0040-N6 — Quality and the assessment boundary**
>
> Recording quality is not assessing evidence. Consistent with Note
> RFC0080-N9, the framework does not judge whether a given quality suffices
> for a given claim — that remains a use-case decision under the governance
> of whoever makes the claim. What the model guarantees is that Quality
> Statements, with their methods and validity, are positioned and resolvable,
> so the use-case judgement can be made without out-of-band knowledge.
> Unknown quality fails silently; declared quality fails visibly.

> **Note RFC0040-N7 — Lineage and empirical motivation**
>
> The quality model follows ISO 19157, whose data quality element has an
> implementation path into observation infrastructures through the
> SensorThings `resultQuality` attribute. The groundwork implementation
> behind this section carried thematic accuracy (sensor accuracy,
> repeatability, stability), the evaluation method with its date, procedure
> and reference, and the conformance result (pass, explanation) — and
> extended the standard with an element correction holding a symbolic
> compensation function evaluable in stream processing. The empirical
> motivation is blunt: in the referenced deployment, low-cost CO₂ sensors
> reported concentrations below the outdoor fresh-air baseline even after
> manufacturer-advised calibration, and the analysis could not be completed.
> Quality that is unknown does not merely weaken conclusions; it prevents
> them.

> **Note RFC0040-N3 — The Open311 report, factored**
>
> An Open311 service request bundles two things the framework separates.
> The report itself — a person communicating, at a time, that a property of
> a place or asset is in a certain condition — is an Observation: observer
> the reporting citizen, observed property drawn from the service taxonomy,
> result the category and description, subject resolved or asserted to a
> Spatial Referent. What the report triggers — receipt, classification,
> dispatch, resolution — is process, and belongs to Activity (RFC 0050),
> referencing the same referent. This factoring confirms the assumption
> recorded in RFC0080-I2: civic reports are representable as observations,
> and the population domain may consume them in the Perception Signal role
> without new machinery.

> **Note RFC0040-N4 — Observation and state**
>
> Observation and state divide the epistemic labour: an Observation is an
> immutable event asserting that an estimate was made; state (RFC 0030) is
> a revisable interpretation of what is currently the case. The two shall
> not be conflated: a thermometer reading is not the temperature of the
> room, and a complaint is not the condition of the park. RFC 0030 is
> expected to define state on this basis, with observations as the evidence
> class state estimation consumes.

# Semantic Relationships

An Observation:

- **is performed by** exactly one Observer;
- **estimates** exactly one Observed Property;
- **produces** exactly one Result;
- **is about** a Subject; when the Subject is spatial, the Subject **is
  identified by** a Spatial Referent, through an asserted or resolved
  binding;
- **is qualified by** time, and by the Observer's location where relevant
  to the pattern in use;
- **may belong to** one or more Observation Series;
- **may serve as** evidence in roles defined by consuming domains, such as
  the Perception Signal role (RFC0080-D4);
- **may be qualified by** Quality Statements, resolvable through its Result,
  its Observer or its Series.

Additionally: a Quality Evaluation **is** an Observation whose Subject is a
Result, an Observer or an Observation Series, and **produces** a Quality
Statement; a Correction **derives** new Observations or Series from existing
ones by a stated function, **referencing** the originals; an Observation
Series **may declare** a Series Scope within which its Subjects are found.

# Design Principles

## Principle RFC0040-P1 — Observer Neutrality Principle

> The framework **shall not** distinguish Observations semantically by the
> nature of their Observer. Instrument, human and computational observations
> share one model; their differences are provenance.

## Principle RFC0040-P2 — Subject Binding Principle

> Every Observation about a spatial entity **shall** bind its Subject to a
> Spatial Referent, either by assertion or by resolution.

## Principle RFC0040-P3 — Observation Immutability Principle

> An Observation records an act and **shall not** be altered.
> Reinterpretation, correction and improved resolution **shall** produce new
> records that reference the original.

# Normative Requirements

> **Requirement RFC0040-R1 — Minimal observation content**
>
> An Observation shall reference its Observer, its Observed Property, its
> Result, its Subject and the time of the act.

---

> **Requirement RFC0040-R2 — Distinguishable locations**
>
> The location of the Observer and the identity of the Subject shall be
> distinguishable. Neither shall be inferred to be the other by default.

---

> **Requirement RFC0040-R3 — Binding provenance**
>
> The binding of a Subject to a Spatial Referent shall record its mode,
> asserted or resolved. A resolved binding shall be revisable by a new
> record without alteration of the Observation.

---

> **Requirement RFC0040-R4 — Observer provenance without person-level identity**
>
> An Observation shall identify its Observer sufficiently to establish
> provenance. For human Observers, this shall not require persistent
> person-level identity, consistent with RFC0080-R4.

---

> **Requirement RFC0040-R5 — Vocabulary binding**
>
> Observed Properties should be defined by reference to externally governed
> vocabularies rather than by vocabularies minted within an observing
> system. Where a local taxonomy exists, as in civic reporting categories,
> it should be mapped to such a vocabulary rather than replaced.

---

> **Requirement RFC0040-R6 — Series coherence**
>
> An Observation Series shall hold constant its Observer, its Observed
> Property, and its Subject or subject pattern. Changes to any of these
> shall begin a new Series.

---

> **Requirement RFC0040-R7 — Quality scope**
>
> A Quality Statement shall declare its scope: a Result, an Observer or an
> Observation Series. When scoped to an Observer or a Series, it shall
> declare its period of validity.

---

> **Requirement RFC0040-R8 — Evaluation provenance**
>
> A Quality Statement shall reference the Quality Evaluation that produced
> it, including the method, the time, and, where conformance is stated, the
> specification against which it was evaluated.

---

> **Requirement RFC0040-R9 — Resolvability**
>
> Applicable Quality Statements shall be resolvable from the Observations
> they qualify. A consumer holding an Observation shall be able to reach the
> quality of its Result, its Observer and its Series without out-of-band
> knowledge.

---

> **Requirement RFC0040-R10 — Correction as derivation**
>
> A Correction shall produce new Observations or Series that reference the
> originals and the correction function applied, and shall not alter the
> originals. The correction function should be recorded in the quality
> metadata of the Observer or Series it compensates.

---

> **Requirement RFC0040-R11 — Series Scope**
>
> An Observation Series whose subject pattern is spatial should declare a
> Series Scope. Whether a Series Scope is declared or derived shall be
> distinguishable. The Subjects of a Series' Observations should lie within
> its Series Scope; a Subject outside the scope indicates either a scope
> revision or a binding error.

# Examples

> **Example RFC0040-E1 — One gateway, many lamp posts**
>
> A public lighting system exposes a single gateway through which thousands
> of luminaires report. The gateway is the observing arrangement; it is not
> what the observations are about. Each Observation's Subject is the
> individual lamp post — a Spatial Referent with its own asset record — or
> the area it illuminates. The subject-located pattern keeps the fact that
> one Observer serves many Subjects from collapsing into a single
> meaningless location.

---

> **Example RFC0040-E2 — A citizen reports a broken bench**
>
> A resident reports a broken bench through a civic reporting channel,
> standing some metres away from it. The Observation carries the citizen as
> Observer (without persistent personal identity), the reporting category
> and free-text description as Observed Property and Result, and the
> reported position as input to resolution. If the resident selected the
> bench from a map, the binding is asserted; if the system matched the
> position to the nearest furniture referent by Anchor Geometry, it is
> resolved, and remains revisable if a better match emerges. The repair
> process that follows is Activity (RFC 0050) against the same referent;
> the population domain may cite the same Observation in the Perception
> Signal role.

---

> **Example RFC0040-E3 — Sensor on a bus**
>
> An air quality sensor mounted on a bus produces a trace-located Series:
> each Observation is qualified by the bus's position at observation time.
> For analysis, each Observation's Subject is resolved to the street
> segment referent containing that position. The Series' subject pattern —
> "segment containing the observation position" — is constant even though
> the resolved referent changes with every Observation.

> **Example RFC0040-E4 — Room sensors and a failing CO₂ fleet**
>
> An apartment building's room sensors report temperature, humidity and CO₂
> concentration as Series against apartment referents. A Quality Evaluation
> of the CO₂ Series finds sustained values below the outdoor fresh-air
> baseline — physically impossible — and records failing conformance as
> Quality Statements scoped to those Series, with the evaluation method and
> period. Consumers resolve the statements from the stream itself and
> exclude the CO₂ Series from ventilation analysis; the humidity Series,
> whose evaluations pass, serve as the proxy instead. For a drifting
> temperature sensor, the evaluation yields a compensation function recorded
> in the Series' quality metadata; live processing publishes a corrected,
> derived Series alongside the immutable original, each corrected value
> referencing its source.

---

> **Example RFC0040-E5 — A camera over a parking area**
>
> A camera is mounted to monitor a parking area. The Observer's location is
> the camera's mounting point. The Series Scope is the camera's field of
> view — the total area under surveillance, declared at commissioning. Each
> Observation's Subject is a specific parking spot, defined as a polygon and
> identified as a Spatial Referent, with a boolean occupancy Result. The
> three spatial facts never collapse into one another: the camera is not in
> the area it watches, the field of view is no single spot, and the
> occupancy of a spot is a claim about the spot, not about the camera or its
> view. Discovery works at scope level — a query for observation coverage of
> the parking area finds the Series — while joins work at subject level,
> spot by spot.

# Planned Figures

> **Figure RFC0040-F1 (placeholder)**
>
> The observation model: Observer, Observed Property, Result, Subject and
> time, with the Subject bound to a Spatial Referent.
>
> *[Diagram to be inserted: fig-rfc0040-f1-observation-model.svg]*

---

> **Figure RFC0040-F2 (placeholder)**
>
> The location patterns — observer-located, trace-located, subject-located —
> and the Series Scope, with their correspondence to SensorThings Location,
> HistoricalLocations, observedArea and FeatureOfInterest.
>
> *[Diagram to be inserted: fig-rfc0040-f2-location-patterns.svg]*

---

> **Figure RFC0040-F3 (placeholder)**
>
> Asserted versus resolved subject binding, and revision of a resolved
> binding without alteration of the Observation.
>
> *[Diagram to be inserted: fig-rfc0040-f3-binding-modes.svg]*

---

> **Figure RFC0040-F4 (placeholder)**
>
> The quality model: Quality Statement scopes (Result, Observer, Series),
> Quality Evaluation as an Observation whose Subject is the observing
> arrangement, and Correction as derivation alongside immutable originals.
>
> *[Diagram to be inserted: fig-rfc0040-f4-quality-model.svg]*

# Standards and Implementation Mappings

The following correspondences are informative.

| Framework concept | Implementation binding (informative) |
|---|---|
| Observation | OGC SensorThings `Observation`; ISO 19156 (O&M) observation event; W3C SOSA `sosa:Observation` |
| Observer | SensorThings `Sensor` (instrument) hosted by a `Thing` (platform); SOSA `sosa:Sensor` / `sosa:Platform`; the reporting citizen in Open311 |
| Observed Property | SensorThings `ObservedProperty`, defined by reference to an external vocabulary; Open311 service taxonomy mapped per RFC0040-R5 |
| Result | SensorThings `result`; Open311 category and description |
| Result interpretability | Unit references bound to SI / UCUM for quantitative Results; vocabulary-bound Observed Properties with free-text payload for qualitative Results |
| Subject | SensorThings `FeatureOfInterest` carrying the Spatial Referent's identity; O&M feature of interest |
| Observer location patterns | SensorThings `Location` (observer-located), `HistoricalLocations` (trace-located), `FeatureOfInterest` distinct from `Location` (subject-located) |
| Observation Series | SensorThings `Datastream` |
| Series Scope | SensorThings `Datastream.observedArea`; a declared scope (e.g. a configured field of view) extends the standard's derived usage |
| Resolved binding | Spatial matching against Anchor Geometry (RFC0010-D4) |
| Quality Statement | ISO 19157 data quality element (`DQ_Element`); SensorThings `Observation.resultQuality` |
| Quality Evaluation | ISO 19157 evaluation method: date, procedure, reference document, method type |
| Conformance | ISO 19157 conformance result: pass, explanation |
| Correction function | Element correction extension to ISO 19157 carrying a symbolic compensation expression evaluable in stream processing |

> **Note RFC0040-N5 — Vocabulary infrastructure**
>
> The practice of retrieving observed property definitions from externally
> governed, hierarchically organized vocabularies — rather than embedding a
> fixed schema per use case — follows the approach demonstrated in the
> Helsinki urban platform work, where property definitions were served from
> an ontology service and grounded in unit systems with open licensing.
> RFC0040-R5 generalizes that practice: the observing system borrows its
> semantics by reference, in the same way the wider framework borrows
> classification and representation by reference.

# Open Questions

> **Issue RFC0040-I1 — Derived observations and the evidence boundary**
> *(resolved by RFC 0030)*
>
> A computational Observer may produce Observations derived from other
> Observations — a daily aggregate, a sentiment indicator computed from
> free text. Where is the line between a derived Observation (evidence) and
> a state estimate (claim)? Resolved: RFC 0030 adopts the supersession
> criterion (Note RFC0030-N1) — a record added alongside its predecessors
> and kept as evidence forever is an Observation, however derived; a record
> that replaces its predecessor as the current answer, with the predecessor
> retained as history, is a State Claim. Correction (RFC0040-D9) is an
> instance of the former: derivation by a declared correction function,
> estimating the same property of the same Subject, remains observation.

---

> **Issue RFC0040-I2 — Qualitative results** *(resolved in Draft 0.4)*
>
> Resolved: qualitative Results are payload of Observations on the same
> terms as quantitative ones (Note RFC0040-N8). The framework defines the
> vehicle of collection and the context resolvable around it; analysis and
> interpretation are out of scope. The semiotic treatment planned for RFC
> 0015 may deepen the account of meaning, but nothing in this RFC waits on
> it.

---

> **Issue RFC0040-I3 — Acts that observe and act** *(resolved by RFC 0050)*
>
> An inspection during maintenance both observes (condition found) and acts
> (work done). Resolved: RFC 0050 generalizes the factoring rule of Note
> RFC0040-N3 — acts are Activities; what they record is Observations among
> their outputs; what they change is State Transitions. No mixed-act
> construct is needed.

---

> **Issue RFC0040-I4 — Observing the observer**
>
> In the trace-located pattern, the Observer's position history is itself a
> series of location estimates — observations whose Subject is the
> Observer. Whether this recursion should be modeled explicitly or treated
> as provenance is open. Quality Evaluation (RFC0040-D8) already sanctions
> observations whose Subject is an Observer, which suggests the recursion is
> admissible in general.

# References

- RFC 0000 — Introduction
- RFC 0001 — Design Principles
- RFC 0002 — Terminology and Naming Conventions
- RFC 0010 — Spatial Referent
- RFC 0030 — State (planned)
- RFC 0050 — Activity (planned)
- RFC 0080 — Population
- Editorial Style Guide
- Open Geospatial Consortium, "OGC SensorThings API Part 1: Sensing," OGC
  document 15-078r6, 2016. (informative)
- ISO, "ISO 19156:2023 Geographic information — Observations, measurements
  and samples," Geneva: International Organization for Standardization.
  (informative)
- W3C, "Semantic Sensor Network Ontology (SSN/SOSA)," W3C Recommendation,
  2017. (informative)
- Open311, "A Collaborative Model and Open Standard for Civic Issue
  Tracking." (informative)
- ISO, "ISO 19157-1:2023 Geographic information — Data quality — Part 1:
  General requirements," Geneva: International Organization for
  Standardization. (informative)
- T. Ruohomäki, A. Andra and K. Raivio, "Defining Data-Driven Analytical
  Methods on Improving Energy-Efficiency in Apartment Buildings,"
  *Engineering Proceedings*, vol. 2, no. 68, 2020. (informative)
