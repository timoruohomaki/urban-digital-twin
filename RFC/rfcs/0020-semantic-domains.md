---
rfc: 0020
title: Semantic Domains
status: Draft 0.1
category: Core
---

# Abstract

This RFC consolidates what the framework requires of a Semantic Domain. A
Semantic Domain (RFC0002-D2) is a coherent body of concepts, relationships
and state governed by a particular perspective or authority; this RFC does
not redefine it, but specifies what a domain contributes and how domains
coexist. A domain brings a Domain Vocabulary, Semantic Interpretations of
Spatial Referents, State Variables and claims, Evidence Roles for the
observations it consumes, and Activities and Processes — all under exactly
one Governing Authority.

Two disciplines govern the whole. Non-interference: no domain's
interpretation is a precondition for another's, and consuming one domain
never requires adopting another's vocabulary. Borrowed vocabulary: domains
bind their classifications to externally governed authorities rather than
minting taxonomies, and every property a domain contributes is traceable
either to the domain's own declared vocabulary or to a named external
authority.

# Status of This Document

This document is normative. It elaborates the Semantic Domain of
RFC0002-D2 without redefining it, per the Stable Terminology principle
(RFC0002-P2), and consolidates domain obligations introduced in RFC 0010,
RFC 0030, RFC 0040, RFC 0050, RFC 0060 and RFC 0080.

# Motivation

Every RFC in this series leans on the Semantic Domain, and each has added
to what the term carries: domains own all interpretation including
geometry (RFC 0010), define state models (RFC0030-R1), define evidence
roles and vocabulary-bound observed properties (RFC 0040), run activities
and processes (RFC 0050), form accountability boundaries under a single
authority (RFC 0060), and — in the population domain — provide a complete
worked instance (RFC 0080). Without a consolidating statement, the
domain's obligations exist only as a scatter of cross-references, and a
new domain joining the ecosystem has no single answer to the question:
*what must I bring, and what may I never demand of others?*

The second motivation is classification. Urban entities are classified
along several axes at once — what sector a thing belongs to, what function
it serves, what kind of object it individually is, what it is part of —
and the axes are routinely conflated in practice, producing taxonomies
that entangle sector with function and type with composition. The
framework's position is that these are orthogonal facets, each bound to
an existing external authority, none minted for the occasion.

# Terminology

## Definition

> **Definition RFC0020-D1 — Domain Vocabulary**
>
> The set of concepts, classifications and named properties through which
> a Semantic Domain expresses its interpretations, declared and owned by
> the domain's Governing Authority.

---

> **Definition RFC0020-D2 — Classification Facet**
>
> An orthogonal axis along which a Semantic Domain classifies an entity.
> Recurring facets are kind or sector, function, individual type, and
> composition; classification along one facet does not constrain another.

---

> **Definition RFC0020-D3 — Evidence Role**
>
> A named role, defined by a Semantic Domain, in which the domain admits
> Observations (RFC 0040) as evidence for its claims. The Perception
> Signal (RFC0080-D4) is the population domain's instance.

---

> **Definition RFC0020-D4 — Domain Extension**
>
> The open set of domain-specific properties a Semantic Domain binds to an
> entity beyond the elements of any Shared Contract, admitted under the
> provenance discipline of RFC0020-R5.

## Scope

This RFC specifies:

- what a Semantic Domain contributes: vocabulary, interpretations, state,
  evidence roles, activities;
- the non-interference discipline between domains;
- classification through orthogonal, externally bound facets;
- the provenance discipline of Domain Extensions;
- independent evolution of domains.

## Not in Scope

This RFC does not specify:

- the content of any domain's vocabulary or state model;
- a canonical list of domains (see Note RFC0020-N1);
- governance machinery, defined in RFC 0060;
- catalog, discovery and publication technology;
- ontology languages or vocabulary encodings.

# Core Concepts

## What a domain brings

A Semantic Domain is the unit of perspective and accountability. Joining
the ecosystem, it brings: a Domain Vocabulary declared by its authority;
Semantic Interpretations that reference Spatial Referents by identity
(RFC0010-R3); State Variables and the claims made in them (RFC0030-R1);
Evidence Roles for the observations it consumes; and the Activities and
Processes it performs (RFC 0050). It brings these under exactly one
Governing Authority, within a declared Area of Responsibility
(RFC0060-R2), and it demands nothing of any other domain beyond the
elements of the Shared Contract (RFC0060-R5).

> **Note RFC0020-N1 — No canonical domains**
>
> The framework names no privileged set of domains. The four recurring
> instances of this series — geospatial, observation-oriented, asset
> management, population — reflect the four domains of the Urban Digital
> Twin literature, but they are informative instances, not a taxonomy.
> Even the geospatial domain is *just another domain*: its Geometric
> Interpretations carry no semantic privilege (Note RFC0010-N1), and a
> city may factor its perspectives differently without leaving the
> framework.

## Non-interference

Orthogonality (RFC0001-P2) becomes operational as non-interference: no
domain's interpretation is a precondition for another's. The asset domain
binds a lifecycle record to a referent whether or not the population
domain has interpreted it as a Place; the population domain claims
perceived safety whether or not an asset record exists. A consumer reads
any subset of domains over one referent, and reading one never requires
adopting another's vocabulary. The joins are on identity; the seams
between domains remain visible, and the twin is a federated reading, not
a merged schema.

> **Note RFC0020-N2 — Seams, not seamlessness**
>
> The visible seam is a feature. City information infrastructures reveal
> the seams within the urban fabric rather than delivering the
> seamlessness they promise, and the framework builds on that honesty: a
> cross-domain view is an assembly of independently governed
> interpretations, and presenting it as a unified object would misstate
> both its provenance and its governance.

## Classification: orthogonal facets, borrowed vocabularies

A domain classifies entities along facets, and the facets are orthogonal:
what sector an entity belongs to (kind), what it does (function), what it
individually is (type), and what it is part of (composition) are separate
questions with separately governed answers. A piece of street furniture
may carry its kind from a spatial data theme, its type from a city-object
vocabulary, its function from a service classification, and its
composition from a parent relation — four bindings, four authorities,
none constraining another.

None of these vocabularies is minted. The framework extends the borrowing
discipline of RFC0040-R5 from observed properties to classification in
general: where an externally governed vocabulary exists, the domain binds
to it by reference; where the domain must speak in its own terms, the
vocabulary is declared, owned and published by the domain's authority —
so that even local vocabulary has an answerable owner.

## The Domain Extension and its discipline

Beyond any shared core, a domain binds an open set of case-specific
properties to the entities it interprets. Openness is not anarchy: the
extension is admitted under one rule, that every property either belongs
to the domain's declared vocabulary or is an external reference to a
named authority. This is the provenance discipline of the framework
applied to schema — every attribute has an answerable source, and a
consumer encountering an unfamiliar property can always resolve who
defined it and under what governance.

## Independent evolution

Domains evolve on their own clocks. A vocabulary is extended, a state
model refined, an evidence role added — without any other domain
changing, because nothing crosses the boundary except referent identities
and contract elements, and those are precisely what evolution shall not
break (RFC0010-R4, RFC0060-R5). The framework thereby locates the cost of
change where the change is made, which is what makes an ecosystem of
autonomous authorities maintainable at all.

# Semantic Relationships

A Semantic Domain:

- **is governed by** exactly one Governing Authority (RFC0002-D4), within
  its Area of Responsibility (RFC0060-D1);
- **declares** a Domain Vocabulary and **binds** classifications to
  external authorities where they exist;
- **contributes** Semantic Interpretations referencing Spatial Referents
  by identity;
- **defines** State Variables and **makes** State Claims (RFC 0030);
- **defines** Evidence Roles and **consumes** Observations in them
  (RFC 0040);
- **performs** Activities and Processes (RFC 0050);
- **extends** entities through Domain Extensions under the provenance
  discipline;
- **evolves independently**, preserving referent identities and Shared
  Contract elements.

# Design Principles

## Principle RFC0020-P1 — Non-Interference Principle

> No Semantic Domain's interpretation **shall** be a precondition for
> another domain's interpretation of the same entity. Consuming one
> domain **shall not** require adopting another domain's vocabulary.

## Principle RFC0020-P2 — Borrowed Vocabulary Principle

> A Semantic Domain **should** bind its classifications to externally
> governed vocabularies by reference. Where domain-local vocabulary is
> necessary, it **shall** be declared, owned and published by the
> domain's Governing Authority.

# Normative Requirements

> **Requirement RFC0020-R1 — Single accountable authority**
>
> A Semantic Domain shall be governed by exactly one Governing Authority
> and shall lie within that authority's declared Area of Responsibility.

---

> **Requirement RFC0020-R2 — Declared contribution**
>
> A Semantic Domain shall declare what it contributes: its Domain
> Vocabulary, the State Variables it defines, and the Evidence Roles in
> which it admits Observations.

---

> **Requirement RFC0020-R3 — Facet orthogonality**
>
> Classification along one Classification Facet shall not constrain
> classification along another. A change to an entity's classification in
> one facet shall not require reclassification in any other.

---

> **Requirement RFC0020-R4 — Classification by reference**
>
> A classification shall be expressed by reference to the identifiers of
> the vocabulary that defines it, such that the defining authority is
> resolvable from the classification itself.

---

> **Requirement RFC0020-R5 — Extension provenance**
>
> Every property in a Domain Extension shall either belong to the
> domain's declared Domain Vocabulary or be an external reference to a
> named authority. Properties satisfying neither condition shall not be
> admitted.

---

> **Requirement RFC0020-R6 — Evolution without breakage**
>
> A Semantic Domain may change its vocabulary, state model, evidence
> roles and processes without requiring changes in any other domain. No
> such change shall alter Spatial Referent identities or the elements of
> a Shared Contract.

# Examples

> **Example RFC0020-E1 — One bike rack, four bindings**
>
> A bike rack in a park is classified along four facets: its kind binds
> to a spatial data theme governed by a European infrastructure, its
> individual type to a city-object vocabulary's street furniture class,
> its function to the park's recreational service grouping, and its
> composition to the park through a parent relation. Four authorities
> govern the four vocabularies; none of the bindings constrains another;
> and when the city reorganizes recreational services — a function-facet
> change — the rack's kind, type and composition are untouched, per
> RFC0020-R3.

---

> **Example RFC0020-E2 — A new domain joins**
>
> An urban forestry domain enters the ecosystem: canopy condition and
> habitat value for street and park referents. It declares its vocabulary
> (binding species classification to an external taxonomic authority),
> defines State Variables for canopy state, admits arborist inspections
> and citizen reports in a declared Evidence Role, and signs the Shared
> Contract for referent identities. No existing domain changes anything;
> the day the forestry domain publishes its first State Claim, every
> other domain's interpretations are already joinable to it — through
> identities that existed all along.

---

> **Example RFC0020-E3 — An unfamiliar property, resolved**
>
> A consumer reading a streetlight's asset-domain extension encounters a
> property it does not recognize: a luminaire efficacy attribute. Under
> RFC0020-R5 the property resolves either to the asset domain's declared
> vocabulary — where the authority's definition is published — or to an
> external reference, here a lighting standard's parameter. In neither
> case is the consumer left guessing what an attribute means or who
> answers for it. A property that resolved to neither would never have
> been admitted.

# Planned Figures

> **Figure RFC0020-F1 (placeholder)**
>
> What a domain brings: vocabulary, interpretations, state, evidence
> roles, activities — under one authority, joined to others only through
> referent identities and contract elements.
>
> *[Diagram to be inserted: fig-rfc0020-f1-domain-contribution.svg]*

---

> **Figure RFC0020-F2 (placeholder)**
>
> Four orthogonal Classification Facets of one entity, each bound to a
> different external authority.
>
> *[Diagram to be inserted: fig-rfc0020-f2-facets.svg]*

# Standards and Implementation Mappings

The following correspondences are informative.

| Framework concept | Correspondence (informative) |
|---|---|
| Kind / sector facet | INSPIRE spatial data themes (Annexes I–III) |
| Individual type facet | CityGML thematic classes, e.g. `CityFurniture` |
| Function facet | Functional and land-use classifications; service taxonomies |
| Composition facet | Parent-feature relations, e.g. a `parentFeatureId` attribute |
| Domain Vocabulary publication | SKOS vocabularies served from ontology services |
| Semantic Domain as product boundary | Data mesh data products under federated accountability |
| Non-interference in APIs | Independently served OGC API collections over shared identifiers |

# Open Questions

> **Issue RFC0020-I1 — A shared descriptive core**
>
> Identity is the contractual floor (RFC 0060), and practice suggests a
> small governed core beyond it — geometry via Anchor Geometry, perhaps a
> display name. Is any descriptive element (naming, addressing) common
> enough to standardize across domains, or is even a name domain-owned?

---

> **Issue RFC0020-I2 — The facet set**
>
> Kind, function, type and composition recur, but this RFC deliberately
> stops short of making the four normative. Should the facet set be
> fixed, extensible by declaration, or remain an informative pattern?

---

> **Issue RFC0020-I3 — Domain discovery**
>
> How does a consumer learn which domains hold interpretations of a given
> referent? A catalog is implementation, but whether the framework should
> define the semantic statement "domain D interprets referent R" — a
> discoverable assertion — is open.

---

> **Issue RFC0020-I4 — Derived domains**
>
> An analytics domain consumes other domains' claims and observations and
> produces its own. Non-interference is preserved formally — it demands
> nothing of its sources beyond published interpretations — but its
> claims depend on theirs. Whether such derived domains need explicit
> dependency semantics (for provenance and invalidation) is open.

# References

- RFC 0000 — Introduction
- RFC 0001 — Design Principles
- RFC 0002 — Terminology and Naming Conventions
- RFC 0010 — Spatial Referent
- RFC 0030 — State
- RFC 0040 — Observation
- RFC 0050 — Activity
- RFC 0060 — Governance and Authority
- RFC 0080 — Population
- Editorial Style Guide
- European Commission, Directive 2007/2/EC (INSPIRE), 2007. (informative)
- Open Geospatial Consortium, "OGC City Geography Markup Language
  (CityGML) Part 1: Conceptual Model Standard," OGC 20-010, 2021.
  (informative)
- Z. Dehghani, *Data Mesh: Delivering Data-Driven Value at Scale*.
  Sebastopol: O'Reilly Media, 2022. (informative)
- C. Raetzsch, G. Pereira, L. S. Vestergaard and M. Brynskov, "Weaving
  seams with data: Conceptualizing City APIs as elements of
  infrastructures," *Big Data & Society*, vol. 6, no. 1, 2019.
  (informative)
