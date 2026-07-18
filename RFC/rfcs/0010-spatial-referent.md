---
rfc: 0010
title: Spatial Referent
status: Draft 0.2
category: Core
---

# Abstract

This RFC defines the Spatial Referent, the central connective concept of the
Urban Digital Twin Semantic Framework. A Spatial Referent asserts that a
real-world spatial entity exists and provides the Persistent Identity through
which independently governed Semantic Domains attach their interpretations to
that entity.

A Spatial Referent carries no descriptive properties of its own. Geometry,
classification, state, observations and all other characteristics are Semantic
Interpretations owned by Semantic Domains. The only claim a Spatial Referent
makes is that its entity exists and that all interpretations bound to it
concern the same entity.

# Status of This Document

This document is normative. It derives from the principles established in
RFC 0001 and uses the terminology defined in RFC 0002. Draft 0.2 adds the
geometric evolution discussion (Example RFC0010-E3) and the mapping to the
OGC Points of Interest conceptual model as a minimal realization (Note
RFC0010-N6).

# Motivation

Urban information environments are data-rich but join-poor. Departmental
systems describe the same real-world places and objects — a park, a building,
a street segment, a piece of street furniture — yet no agreed joining element
spans their boundaries. Where cross-domain joins are made, they are typically
produced as one-off exercises by matching copies of geometry or by ad hoc
identifier mapping, neither of which survives institutional or technical
change.

Existing standards each bundle identity with description. An OGC feature
combines an identifier with a geometry and a set of properties; a CityGML
object combines identity with a geometric representation at a level of detail;
an IFC element combines identity with construction semantics. When several
such descriptions concern the same real-world entity, none of them can serve
as the neutral point of agreement, because adopting any one of them as
canonical would subordinate the other domains to its modeling choices —
violating the Orthogonal Semantic Domains Principle (RFC0001-P2) and the
Institutional Autonomy Principle (RFC0001-P5).

The framework therefore isolates the one element all domains must share —
identity and the assertion of existence — into a concept of its own. This
concept plays the role of a shared business key across domains: stable,
meaning-free at the point of joining, and owned by governance rather than by
any single information model.

# Terminology

## Definition

> **Definition RFC0010-D1 — Spatial Referent**
>
> A Persistent Identity that asserts the existence of a real-world spatial
> entity and serves as the common anchor through which Semantic Domains
> associate Semantic Interpretations with that entity.

---

> **Definition RFC0010-D2 — Existence Assertion**
>
> The claim, made by a Governing Authority, that a Spatial Referent
> corresponds to a real-world entity within that authority's area of
> responsibility.

---

> **Definition RFC0010-D3 — Geometric Interpretation**
>
> A Semantic Interpretation that expresses the spatial extent, position or
> shape of the entity referred to by a Spatial Referent, as understood by a
> particular Semantic Domain.

---

> **Definition RFC0010-D4 — Anchor Geometry**
>
> A Geometric Interpretation designated through governance as the reference
> for spatial operations involving a Spatial Referent.

## Scope

This RFC specifies:

- the semantic content of a Spatial Referent;
- the relationship between a Spatial Referent and Semantic Interpretations;
- the persistence and lifecycle expectations of Spatial Referents;
- the mechanism by which spatial joining remains possible when geometry is a
  Semantic Interpretation rather than an intrinsic property.

## Not in Scope

This RFC does not specify:

- how geometries are encoded, stored or served;
- classification or typing of entities (see RFC 0020);
- state and its evolution (see RFC 0030);
- observation semantics (see RFC 0040);
- rules for resolving disputes between Governing Authorities (see RFC 0060);
- identifier syntax, allocation schemes or resolution protocols.

# Core Concepts

## Existence, not description

The Spatial Referent is deliberately minimal. Its entire semantic content is
the Existence Assertion: *this entity exists, and everything bound to this
identity concerns it*. Every descriptive statement — where the entity is, what
it is, what condition it is in, who is responsible for it, who occupies or
uses it — belongs to a Semantic Domain and is expressed as a Semantic
Interpretation referencing the Spatial Referent.

> **Note RFC0010-N1 — Geometry as the first dimension**
>
> Geometry is the interpretation most often mistaken for an intrinsic
> property, because established standards define a feature as the pairing of
> identity and geometry. In this framework geometry has no privileged
> semantic status: it is the interpretation contributed by a geospatial
> Semantic Domain, alongside the asset domain's lifecycle record or the
> population domain's collective scope. Several Geometric Interpretations of
> one Spatial Referent may legitimately coexist — a cadastral footprint, a
> visualization model and a construction model differ in purpose, precision
> and governance, and none is inherently "the" geometry of the entity.

> **Note RFC0010-N2 — Institutional, not ontological, existence**
>
> The Existence Assertion is an institutional act, not a metaphysical one. A
> Spatial Referent exists because a Governing Authority takes responsibility
> for asserting it, consistent with the Governance Authority Principle
> (RFC0001-P4). Entities without physical form — a planning zone, a noise
> abatement area, a statistical district — may be asserted on the same terms
> as buildings and benches.

> **Note RFC0010-N3 — Minimal critical specification**
>
> The design deliberately echoes the socio-technical principle of minimal
> critical specification: no more is specified centrally than is absolutely
> essential. The essential shared element is identity and existence; all
> else remains under the autonomy of the contributing domains.

## Geometry evolves; identity does not

Geometric Interpretations vary not only across domains but across time. A
planned feature enters the model as a point from the plan; the as-built
survey replaces the point with a polygon; annexes later extend the
polygon. Each is a Geometric Interpretation under the geospatial domain's
governance, superseding or joining its predecessors, and the Anchor
Geometry designation moves by governance act as the authoritative shape
improves. The Spatial Referent's identity never moves. Every cross-domain
binding made against the planned point — a permit process, an asset
record, a citizen observation — survives the entire geometric lifecycle,
which is precisely the payoff of Existence Minimalism: had the referent
carried its geometry, every refinement of shape would have threatened
every reference to the thing.

## The referent as shared key

Functionally, the Spatial Referent behaves like a shared business key in a
federated information landscape: the stable element around which
independently governed descriptions accumulate. Joining across domains is
performed on identity, never by comparing descriptive content. Two domains
interoperate on an entity not because their descriptions match but because
they reference the same Spatial Referent.

## Spatial joining without intrinsic geometry

Removing geometry from the referent raises a practical question: spatial
association — finding the referent nearest to a reported position, or the
referent containing a point — requires some geometry to operate on. The
framework resolves this through governance rather than semantics: one
Geometric Interpretation is designated as Anchor Geometry (RFC0010-D4) by the
responsible Governing Authority. The designation confers operational
precedence for spatial operations; it does not confer semantic precedence
over other Geometric Interpretations.

# Semantic Relationships

A Spatial Referent:

- **is identified by** exactly one Persistent Identity (RFC0001-D1);
- **is asserted by** a Governing Authority through an Existence Assertion;
- **is referenced by** any number of Semantic Interpretations, each owned by
  a Semantic Domain;
- **may be related to** other Spatial Referents; such relationships (for
  example composition or succession) are themselves Semantic Interpretations
  owned by the domain making the claim.

> **Note RFC0010-N4 — Composition**
>
> Whether part-of relationships between referents (a bench within a park, a
> building on a parcel) belong to a governed core or to individual domains
> remains an open question (RFC0010-I3). Spatial containment can be derived
> from Geometric Interpretations; functional composition is a domain claim.

# Design Principles

## Principle RFC0010-P1 — Existence Minimalism Principle

> A Spatial Referent **shall** assert the existence and identity of its
> entity, and nothing else.

# Normative Requirements

> **Requirement RFC0010-R1 — Single identity**
>
> A Spatial Referent shall be identified by exactly one Persistent Identity.

---

> **Requirement RFC0010-R2 — No descriptive content**
>
> A Spatial Referent shall carry no descriptive properties. All descriptive
> content, including geometry, shall be expressed as Semantic Interpretations
> within Semantic Domains.

---

> **Requirement RFC0010-R3 — Referential linkage**
>
> A Semantic Domain shall associate its interpretations with a Spatial
> Referent through its Persistent Identity, not through correspondence of
> descriptive content such as matching geometries or names.

---

> **Requirement RFC0010-R4 — Persistence**
>
> The Persistent Identity of a Spatial Referent shall remain stable across
> changes to any Semantic Interpretation, and shall never be reused for a
> different entity.

---

> **Requirement RFC0010-R5 — Lifecycle of existence**
>
> An Existence Assertion may be withdrawn when the entity ceases to exist.
> Withdrawal shall not invalidate the Persistent Identity: historical
> interpretations remain resolvable against the retired referent.

---

> **Requirement RFC0010-R6 — Anchor Geometry**
>
> At least one Geometric Interpretation should be designated as Anchor
> Geometry for each Spatial Referent. The designation shall be a governance
> act and shall not imply semantic precedence over other Geometric
> Interpretations.

# Examples

> **Example RFC0010-E1 — Street furniture in a municipal park**
>
> A city asserts a Spatial Referent for a bike rack in a park. The geospatial
> domain contributes a point geometry, designated as Anchor Geometry. The
> asset management domain binds a lifecycle record with condition and
> maintenance history. The observation domain treats the referent as the
> feature of interest for usage counts. Citizen feedback about the rack is
> associated with the same referent through spatial matching against the
> Anchor Geometry. The population domain interprets the surrounding park —
> itself a Spatial Referent — as the spatial scope of a collective of users
> (see RFC 0080). Five domains, five governance arrangements, one identity.

---

> **Example RFC0010-E2 — One building, several geometries**
>
> A building carries three Geometric Interpretations: a cadastral footprint
> governed by the land registry, a visualization model governed by the city
> model team, and a construction model governed by the building's owner. All
> reference the same Spatial Referent. The cadastral footprint is designated
> Anchor Geometry for spatial operations. No interpretation is "the" geometry
> of the building; replacing the construction model after renovation changes
> nothing about the referent or the other interpretations.

---

> **Example RFC0010-E3 — From plan to building to annex**
>
> A new community building is asserted as a Spatial Referent at planning
> time, its only Geometric Interpretation a point taken from the plan, and
> that point designated Anchor Geometry. The permit process (an Activity)
> binds to the referent; early citizen feedback about the plan resolves to
> it through the point. At completion, the as-built survey contributes a
> polygon; the Anchor Geometry designation moves to it by governance act,
> and the point remains as the planning domain's historical interpretation.
> Years later two annexes extend the footprint, and the polygon is
> superseded again. Across point, polygon and extended polygon, the
> referent's identity is untouched: the permit history, the asset records
> opened at handover and the accumulated citizen observations all join the
> same building through all three of its shapes.

# Planned Figures

> **Figure RFC0010-F1 (placeholder)**
>
> The Spatial Referent as the hub of Semantic Interpretations contributed by
> independently governed Semantic Domains.
>
> *[Diagram to be inserted: fig-rfc0010-f1-referent-hub.svg]*

---

> **Figure RFC0010-F2 (placeholder)**
>
> Multiple Geometric Interpretations of one Spatial Referent, with one
> designated as Anchor Geometry.
>
> *[Diagram to be inserted: fig-rfc0010-f2-geometric-interpretations.svg]*

# Standards and Implementation Mappings

The following correspondences are informative. They identify implementation
constructs capable of realizing the Spatial Referent's identity, not
equivalents of the concept: each listed construct bundles identity with
descriptive content that this framework assigns to Semantic Domains.

| Framework concept | Implementation binding (informative) |
|---|---|
| Spatial Referent identity | OGC Simple Features `feature_id`; INSPIRE External Object Identifier (namespace, localId, versionId) |
| Referent as feature of interest | OGC SensorThings `FeatureOfInterest` |
| Geometric Interpretation | OGC Simple Features geometry; CityGML object geometry; IFC model referenced by URI |
| Existence Assertion lifecycle | INSPIRE identifier persistence and versioning governance; OGC POI lifespan properties |
| Minimal realization | OGC Points of Interest Conceptual Model (OGC 21-049): "a set of coordinates and an identifier" as the minimal POI |

> **Note RFC0010-N5 — Relationship to the OGC feature**
>
> The OGC feature is the closest implementation relative of the Spatial
> Referent and the natural carrier of its identity in practice. The
> conceptual difference is one of factoring: the OGC feature bundles
> identity, geometry and properties into one construct, whereas this
> framework treats the identity as the referent and the geometry and
> properties as interpretations. An OGC feature published with a persistent
> identifier can therefore serve simultaneously as the realization of a
> Spatial Referent and as the geospatial domain's Geometric Interpretation
> of it.

> **Note RFC0010-N6 — A minimal realization: the OGC Point of Interest**
>
> Among published standards, the OGC Points of Interest Conceptual Model
> (OGC 21-049) comes closest to an existence-minimal referent: it admits a
> POI "as simple as a set of coordinates and an identifier," and three of
> its design choices align with this framework's machinery arrived at
> independently. Its lifespan properties distinguish database time
> (creation, termination) from real-world time (validFrom, validTo) —
> the two-times discipline of RFC 0030 and the existence lifecycle of
> RFC0010-R5. Its identifier model admits a local featureID alongside
> additional scoped identifiers — the identity–identifier separation of
> RFC 0015. And its payload mechanism requires extensions to reference
> external schemas — the Domain Extension provenance discipline of
> RFC0020-R5. The caveat is the same as for the OGC feature (Note
> RFC0010-N5): the POI still bundles a location and descriptive slots
> with its identity, so it is a minimal *carrier* of a Spatial Referent
> rather than the pure concept — the framework reads the POI's geometry
> as a Geometric Interpretation (and Anchor Geometry candidate) and its
> payloads as Domain Extensions. Read this way, the POI model is a
> natural publication form for referents whose authoritative geometry is
> still coarse or evolving, as in Example RFC0010-E3.

# Open Questions

> **Issue RFC0010-I1 — Anchor Geometry mechanism**
>
> Is governance-designated Anchor Geometry the right mechanism for spatial
> joining, or should the referent carry a minimal existence locator of its
> own? The current design favors governance designation to preserve
> Existence Minimalism.

---

> **Issue RFC0010-I2 — Minting and reconciliation** *(resolved by RFC 0060)*
>
> Which authorities may assert Spatial Referents, and how are duplicate
> assertions for the same real-world entity reconciled? Resolved: any
> Governing Authority may assert referents within its declared Area of
> Responsibility, carrying the persistence obligations of this RFC
> (RFC0060-R3). Duplicates are reconciled by a correspondence Governance
> Act without deletion; a primary identity may be designated for joining,
> as operational precedence only (RFC0060-R4).

---

> **Issue RFC0010-I3 — Composition in core or in domains**
>
> Should part-of relationships between referents belong to a governed core,
> or remain domain-owned interpretations (see Note RFC0010-N4)?

---

> **Issue RFC0010-I4 — Temporal identity and succession**
>
> How are splitting and merging of entities (for example cadastral parcels)
> represented — as succession relationships between referents, or within a
> temporal identity model? Related to the open question on temporal identity
> in RFC 0001 and to Issue RFC0015-I1. One boundary is now fixed by Example
> RFC0010-E3: geometric evolution, however extensive, is a succession of
> Geometric Interpretations, not of entities — succession concerns the
> entity itself.

# References

- RFC 0000 — Introduction
- RFC 0001 — Design Principles
- RFC 0002 — Terminology and Naming Conventions
- RFC 0080 — Population (planned)
- Editorial Style Guide
- Open Geospatial Consortium, "OGC Simple Features Access — Part 1: Common
  Architecture," OGC document 06-103r4, 2011. (informative)
- Open Geospatial Consortium, "OGC API — Features — Part 1: Core," OGC
  document 17-069r4, 2022. (informative)
- Open Geospatial Consortium, "OGC SensorThings API Part 1: Sensing," OGC
  document 15-078r6, 2016. (informative)
- Open Geospatial Consortium, "OGC Points of Interest Conceptual Model
  Standard 1.0," OGC document 21-049. (informative)
- European Commission, Directive 2007/2/EC (INSPIRE), 2007. (informative)
