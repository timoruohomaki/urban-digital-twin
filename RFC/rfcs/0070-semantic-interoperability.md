---
rfc: 0070
title: Semantic Interoperability
status: Draft 0.1
category: Core
---

# Abstract

This RFC assembles the framework's machinery into its purpose: semantic
interoperability among independently governed domains. Interoperability is
defined as the ability of such domains to use each other's information
with meaning preserved — achieved through shared identity and resolvable
references, never through shared schemas or centralized models.

The pattern is federation by reference, applied at four layers. Data is
joined at the Spatial Referent; classification semantics bind to external
vocabularies; heavyweight geometric models are referenced, not absorbed;
and computation is invoked through interfaces keyed to identity, returning
results on identity. Interoperability delivers value at the identity floor
alone and scales with each explicitly added contract element — the twin
that results is not a platform to be built but a data space to be
governed.

# Status of This Document

This document is normative. It is the capstone of the RFC series,
assembling the constructs of RFC 0010 through RFC 0080 into the
framework's interoperability architecture. It introduces little new
machinery deliberately: interoperability is what the preceding RFCs,
taken together, already provide.

# Motivation

Cities are data-rich and join-poor: the datasets exist, the joins do not,
and the missing element is not tooling but an agreed joining discipline
that spans departmental boundaries without violating their autonomy. The
alternatives on offer both fail the framework's principles. The
centralized platform — one model, one schema, one owner — buys joins at
the price of sovereignty and has failed institutionally wherever
semantics could not be commanded. The purely bilateral integration — a
mapping per pair of systems — preserves autonomy at quadratic and
perishable cost.

The framework's answer has been built across this series piece by piece:
identity without description (RFC 0010), interpretation without hierarchy
(RFC 0015, RFC 0020), evidence and state with declared ground (RFC 0040,
RFC 0030), processes with visible boundaries (RFC 0050), and authority
with minimal explicit contracts (RFC 0060). This RFC states what those
pieces jointly achieve, and names the conformance question: what must
hold for two domains to be semantically interoperable in this
framework's sense.

# Terminology

## Definition

> **Definition RFC0070-D1 — Semantic Interoperability**
>
> The ability of independently governed Semantic Domains to use each
> other's information with meaning preserved, achieved through shared
> Persistent Identity and resolvable references to answerable
> authorities, without shared schemas, shared models or centralized
> ownership.

---

> **Definition RFC0070-D2 — Federation by Reference**
>
> The pattern by which a layer of the interoperability architecture is
> provided by referencing an existing authority rather than by
> centralizing a replacement: data at its source, vocabulary at its
> authority, model at its custodian, computation at its host.

---

> **Definition RFC0070-D3 — Join**
>
> The operation associating interpretations across Semantic Domains. An
> identity join proceeds directly on shared Spatial Referent identity; a
> spatial join first resolves a position to an identity against Anchor
> Geometries, then proceeds as an identity join.

## Scope

This RFC specifies:

- the definition of semantic interoperability for this framework;
- the four federated layers: data, semantics, model, computation;
- the join and its two forms;
- preservation of identity and provenance in derived products;
- the maturity gradient: value at the floor, scaling by explicit
  addition.

## Not in Scope

This RFC does not specify:

- API designs, encodings and protocols;
- conformance test suites (see Issue RFC0070-I1);
- mappings to other semantic frameworks (see Issue RFC0070-I2);
- performance, availability and other operational qualities.

# Core Concepts

## The four federated layers

Interoperability is federated by reference at four layers, each governed
by the discipline of an earlier RFC.

**Data.** Departmental datasets are joined at the Spatial Referent
without leaving their source systems. The join key is the identity; the
contract floor (RFC0060-D3) is the agreement to use it consistently.
Nothing else about a participant's data is touched.

**Semantics.** Classifications bind to externally governed vocabularies
by reference (RFC0020-P2, RFC0040-R5). A consumer resolves what a
classification means from the authority that defines it — across
domains, without a shared schema and without a minted master taxonomy.

**Model.** Heavyweight geometric representations are referenced, not
absorbed. A building's construction model or a district's city model
remains with its custodian, reachable through a typed reference from the
feature that carries the identity; the representation referenced scales
with the asset, and the twin is heterogeneous by representation while
unified by identity.

**Computation.** Analytics are invoked through interfaces keyed to
identity: a computation accepts referent identities or an area of
interest, dereferences whatever models and data its execution requires —
at their sources, under their governance — and returns results keyed to
the same identities. In its strongest form the computation moves to
where the data sovereignly resides, and only results travel.

> **Note RFC0070-N1 — A data space to be governed**
>
> Assembled this way, the Urban Digital Twin is not a platform to be
> built. It is a data space to be governed: a set of decisions by
> autonomous authorities to treat the geospatial feature's identity as
> their minimal common contract, to reference rather than centralize at
> every layer above it, and to let the seams between their domains
> remain visible. The entry cost is institutional coordination; the
> technical precondition is only that participants publish
> standards-conformant features with stable identities.

## The join, and what it preserves

Every cross-domain use passes through the join (RFC0070-D3). Identity
joins are exact and are the steady state; spatial joins are the entry
path for anything that arrives with only a position — a citizen report,
a sensor trace — and end, by resolution against Anchor Geometries, in
identity. The framework's binding-mode discipline (RFC0040-R3) travels
with the join: what was asserted and what was resolved remains
distinguishable downstream.

Derived products preserve what they consumed. An enriched view, a mart
table, an analytical result carries the referent identities of its
inputs — never re-keyed, per RFC0010-R4 and RFC0015-R2 — and remains
attributable through the chain of domains, claims and evidence it drew
on. Interoperability that strips identity or provenance in its outputs
consumes the commons it depends on.

## The maturity gradient

Interoperability delivers value at the floor and scales by explicit
addition, never by demand. With identity alone, datasets join and
per-capita indicators emerge. Each further contract element — a
resolution delegation, a designated vocabulary binding, shared evidence
roles, process handoffs — adds analytical depth without architectural
change. The gradient is a design property, not an accident: no
participant is asked for more than the floor to begin, and no addition
forces renegotiation of what already works
(RFC0060-P1, RFC0020-R6).

> **Note RFC0070-N2 — The evidence loop as interoperability test**
>
> The closed evidence loop — an observation triggers a process, the
> process effects a transition, the new state is observed again, all on
> one referent (Figure RFC0050-F3) — exercises every layer: data joins,
> vocabulary resolution, state and evidence machinery, activity
> boundaries, and at least two authorities. A city that can run one such
> loop end-to-end has demonstrated semantic interoperability in this
> framework's sense; a city that cannot knows exactly which layer is
> missing. The loop is thus the practical conformance probe, prior to
> any formal test suite.

# Semantic Relationships

Semantic Interoperability **is achieved when**:

- participating domains **share** Spatial Referent identities under a
  Shared Contract (RFC 0060);
- their interpretations **are attributable** and their references
  **resolve** to answerable authorities (RFC 0015, RFC 0020);
- their evidence and state **carry** declared ground and mode (RFC 0040,
  RFC 0030);
- their processes **expose** boundaries at which state and
  responsibility change (RFC 0050);
- joins **preserve** identity and provenance into derived products.

# Design Principles

## Principle RFC0070-P1 — Reference over Centralization Principle

> Interoperability **shall** be achieved by reference to existing
> authorities at every layer — data, semantics, model, computation.
> Participation **shall not** require centralizing data, adopting a
> master vocabulary, materializing a unified model, or hosting shared
> computation.

## Principle RFC0070-P2 — Floor Value Principle

> The interoperability arrangement **shall** deliver value at the
> identity floor alone, and **shall** scale through explicitly agreed
> additions. No participant **shall** be required to exceed the floor as
> a condition of participation.

# Normative Requirements

> **Requirement RFC0070-R1 — Joins end in identity**
>
> Cross-domain association shall be expressed as identity joins. A
> spatial join shall resolve to a Spatial Referent identity and proceed
> as an identity join; the resolution shall record its binding mode per
> RFC0040-R3.

---

> **Requirement RFC0070-R2 — Resolvable references**
>
> Every cross-boundary reference — to a vocabulary term, a geometric
> model, a Governance Act, a Quality Statement — shall resolve to the
> authority that answers for it.

---

> **Requirement RFC0070-R3 — Models by reference**
>
> Heavyweight geometric or construction models shall be referenced from
> the identity-bearing feature, not absorbed into a centralized model.
> The referenced representation may scale with the asset.

---

> **Requirement RFC0070-R4 — Computation on identity**
>
> Cross-domain computation should be exposed through interfaces that
> accept referent identities or areas of interest and return results
> keyed to referent identities, executing where its sources sovereignly
> reside wherever feasible.

---

> **Requirement RFC0070-R5 — Provenance through derivation**
>
> Derived products shall preserve the Spatial Referent identities of
> their inputs and shall remain attributable to the domains, claims and
> evidence they consumed. Derivation shall not re-key identity.

# Examples

> **Example RFC0070-E1 — One report, four domains, one decision**
>
> A citizen reports an unsafe corner. The spatial join resolves the
> position to a crossing referent (mode: resolved); the identity join
> then reaches the asset domain's lighting records, the observation
> domain's pedestrian counts, and the population domain's perceived
> safety claims for the surrounding place — four domains, three
> authorities, no shared schema. The analysis supporting the lighting
> decision cites claims whose evidence and ground are inspectable down
> to the original observations, and the decision's effect returns
> through the evidence loop as a new state, on the same identity.

---

> **Example RFC0070-E2 — Solar yield without a city model**
>
> An energy analysis needs roof geometry the connector layer does not
> hold. The computation interface accepts a district as area of
> interest, dereferences each building's referenced model at its
> custodian, computes irradiation where the models reside, and returns
> yield per building referent. No unified 3D city model was built; the
> buildings' representations differ in fidelity and format; the results
> join every other domain by identity the moment they return.

---

> **Example RFC0070-E3 — The join transfers between cities**
>
> A spatial-join model written against one city's standards-conformant
> transport network transfers to another city with the same annex
> compliance, because the schema it joins against is the standard's, not
> the city's. What does not transfer automatically — the contract, the
> delegations, the designations — is precisely the institutional part,
> which is the framework's claim: the technology of interoperability is
> reusable; its governance must be enacted anew, and is the smaller
> task.

# Planned Figures

> **Figure RFC0070-F1 (placeholder)**
>
> The four federated layers — data, semantics, model, computation — each
> referencing its authority, joined by the Spatial Referent identity.
>
> *[Diagram to be inserted: fig-rfc0070-f1-four-layers.svg]*

---

> **Figure RFC0070-F2 (placeholder)**
>
> The maturity gradient: value at the identity floor, scaling by
> explicit contract additions without architectural change.
>
> *[Diagram to be inserted: fig-rfc0070-f2-maturity-gradient.svg]*

# Standards and Implementation Mappings

The following correspondences are informative.

| Framework concept | Correspondence (informative) |
|---|---|
| Data layer join | OGC API Features collections over PostGIS; INSPIRE data products as the trusted spatial backbone |
| Semantics layer | INSPIRE themes, CityGML classes, SKOS vocabularies referenced by URI |
| Model layer | CityGML and IFC models referenced by typed URI from the identity-bearing feature |
| Computation layer | OGC API Processes: invocation by feature identity or area of interest, results keyed to identity |
| Shared Contract floor | IDS connector registration; data space participation agreements |
| Spatial join entry path | Nearest-feature and containment resolution against Anchor Geometries |

# Open Questions

> **Issue RFC0070-I1 — Conformance classes**
>
> Should the framework define testable conformance classes — for
> example: identity floor, resolvable semantics, closed evidence loop —
> so that a city can state its interoperability level verifiably? The
> evidence loop of Note RFC0070-N2 suggests the highest class; the
> lower boundaries need definition.

---

> **Issue RFC0070-I2 — Other frameworks**
>
> Urban platforms built on other semantic foundations — context
> information models, linked-data city ontologies — hold information
> this framework's domains could use. Whether mappings to such
> frameworks belong in this series' `mappings/` collection, and what
> the identity-correspondence discipline is across framework
> boundaries, is open.

---

> **Issue RFC0070-I3 — Version drift across the federation**
>
> Federation by reference makes the framework dependent on the
> stability of the referenced authorities: vocabulary versions, model
> releases, contract amendments. RFC0015-I2 raises the meaning-drift
> half; the operational half — how a federation coordinates versioned
> references without central release management — is open here.

---

> **Issue RFC0070-I4 — Measuring the gradient**
>
> The maturity gradient is qualitative. Whether useful quantitative
> indicators exist — coverage of referent identities across systems,
> proportion of resolvable references, loop closure rates — and whether
> the framework should suggest them, is open.

# References

- RFC 0000 — Introduction
- RFC 0001 — Design Principles
- RFC 0002 — Terminology and Naming Conventions
- RFC 0010 — Spatial Referent
- RFC 0015 — Identity, Meaning and Interpretation
- RFC 0020 — Semantic Domains
- RFC 0030 — State
- RFC 0040 — Observation
- RFC 0050 — Activity
- RFC 0060 — Governance and Authority
- RFC 0080 — Population
- Editorial Style Guide
- Open Geospatial Consortium, "OGC API — Features — Part 1: Core," OGC
  17-069r4, 2022. (informative)
- Open Geospatial Consortium, "OGC API — Processes — Part 1: Core," OGC
  18-062r2, 2021. (informative)
- International Data Spaces Association, "IDS Reference Architecture
  Model 4.0," 2022. (informative)
- European Commission, Directive 2007/2/EC (INSPIRE), 2007.
  (informative)
