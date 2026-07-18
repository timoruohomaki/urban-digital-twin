---
rfc: 0015
title: Identity, Meaning and Interpretation
status: Draft 0.1
category: Core
---

# Abstract

This RFC provides the semantic grounding of the framework's central
separation: identity is independent of meaning (RFC0001-P1). The grounding
is semiotic. The framework's three-way structure — the real-world entity,
the Persistent Identity that stands for it, and the Semantic
Interpretations that give it meaning — is the classical triangle of
reference, with one deliberate refinement: the relation between sign and
entity, which semiotics has always drawn as imputed rather than direct, is
made explicit here as an institutional act, the Existence Assertion.

Two practical distinctions follow. Identity is not identifier: one
Persistent Identity may be realized by many identifiers, and sameness is
established by correspondence acts, never by string equality. And
interpretation is not designation: meanings coexist plurally, while
governance may select one for a stated operational purpose — a Designation
— conferring operational precedence without semantic precedence. This RFC
defines Designation as a first-class concept, giving the series' recurring
figure its formal home.

# Status of This Document

This document is normative. It grounds and elaborates RFC0001-P1 and the
Semantic Interpretation of RFC0002-D3 without redefining them, and gives
formal footing to constructs introduced in RFC 0010, RFC 0060 and RFC
0080.

# Motivation

The framework asks its users to hold three things apart that everyday
practice fuses: the thing in the world, the identity that refers to it,
and the meanings attached to it. When these fuse, familiar pathologies
follow. Fusing identity with meaning makes every reclassification an
identity crisis — rename the category and the joins break. Fusing
identity with identifier makes every system migration a loss of history —
re-key the database and the references dangle. Fusing meaning with the
entity itself produces the "true meaning" fallacy — one domain's
interpretation promoted to the thing's essence, subordinating every other
domain (the mistake RFC 0010 diagnoses in treating one geometry as *the*
geometry).

Semiotics dismantled this fusion a century ago: meaning is a triadic
relation among a sign, the thing it stands for, and the interpretation
that connects them — and the sign touches the thing only through
convention. The framework does not need the philosophy; it needs the
discipline. This RFC states it once, so the other RFCs can rest on it.

# Terminology

## Definition

> **Definition RFC0015-D1 — Identifier**
>
> A realization of a Persistent Identity within a particular system or
> naming scheme. One Persistent Identity may be realized by many
> Identifiers.

---

> **Definition RFC0015-D2 — Designation**
>
> A Governance Act selecting one among coexisting Semantic
> Interpretations, or one among corresponding identities, for a stated
> operational purpose. A Designation confers operational precedence within
> its purpose and no semantic precedence beyond it.

## Scope

This RFC specifies:

- the triadic structure of entity, identity and interpretation;
- the distinction between Persistent Identity and Identifier, and the
  establishment of sameness;
- the distinction between interpretation and Designation;
- the treatment of reference failure.

## Not in Scope

This RFC does not specify:

- identifier syntax, allocation or resolution technology;
- any domain's interpretations or vocabularies (RFC 0020);
- the governance machinery of acts and contracts (RFC 0060);
- a philosophical theory of meaning beyond what the framework's
  discipline requires.

# Core Concepts

## The triangle, institutionalized

The classical triangle of reference relates a symbol, a thought or
interpretation, and a referent — with the base of the triangle, from
symbol directly to referent, drawn as an imputed relation: the sign
reaches the thing only through interpretation and convention, never
directly. The framework instantiates the triangle as follows: the
real-world entity stands at the referent corner; the Persistent Identity
is the symbol; and each Semantic Domain contributes an interpretation at
the third corner — many interpretations, one per interpreting domain,
where the classical picture drew one.

The framework's refinement is to make the imputed base explicit and
institutional. What fixes a Persistent Identity to a real-world entity is
not resemblance or description — the identity carries no description
(RFC0010-R2) — but the Existence Assertion (RFC0010-D2): a Governance Act
by which an authority takes responsibility for the imputation. The dashed
line of the semiotic diagram becomes an answerable institutional
commitment, revisable through the referent lifecycle (RFC0010-R5) when
the imputation fails.

> **Note RFC0015-N1 — Meaning is domain-relative, and that is the point**
>
> With many interpreting domains, the question "what does this entity
> really mean?" has no answer in the framework — deliberately. There is
> no interpretant-of-interpretants, no master ontology adjudicating among
> domains. What replaces "true meaning" is *answerable meaning*: every
> interpretation is attributable to a domain under an authority
> (RFC0030-R2, RFC0020-R1), and where operations require a single answer,
> a Designation supplies one for that purpose. The framework trades
> semantic finality for semantic accountability.

## Identity is not identifier

A Persistent Identity is the conceptual sameness-anchor; an Identifier is
its realization in a system. The bridge of Example RFC0060-E2 has one
identity and two identifiers, one per asserting authority, related by a
correspondence act. The practical rules follow directly: sameness of
identity is established by correspondence (RFC0060-R4), never inferred
from equality or similarity of identifier strings; and difference of
identifiers implies nothing about difference of entities. Migrating a
system re-keys identifiers; it must never re-key identity — which is what
RFC0010-R4's persistence obligation protects.

## Interpretation is not designation

Interpretations answer *what does this mean to this domain*; Designations
answer *which answer shall this operation use*. The series has needed
this distinction repeatedly — Anchor Geometry among Geometric
Interpretations (RFC0010-D4), the primary identity among reconciled
identifiers (RFC0060-R4) — and each time has insisted that the selection
confers operational precedence only. This RFC names the pattern once:
those constructs are Designations (RFC0015-D2), and any future selection
of the same shape — a designated display name, a designated address —
inherits the same discipline: stated purpose, operational precedence
within it, semantic precedence nowhere.

## Reference failure is normal

A framework built on imputation must expect imputation to fail, and the
series' machinery is largely semiotic repair under another name. A
resolved subject binding that matched the wrong referent (RFC0040-R3) is
a reference failure, corrected by a new record. Duplicate referents
(RFC0060-R4) are two signs imputed to one entity, repaired by
correspondence. A withdrawn Existence Assertion (RFC0010-R5) is an
imputation given up — the entity ceased, or never was — with the sign
retained so history keeps resolving. None of these requires metaphysics;
all of them require that repair never erase (RFC0030-P1's discipline,
applied to reference).

> **Note RFC0015-N2 — Collective meaning**
>
> When the population domain claims the attributed meaning of a Place
> (RFC0080-D3), the interpreting position is held by a collective: the
> meaning of a square to its residents is an interpretation whose
> interpreter is the collective itself, irreducible to member
> interpretations per the Collective Irreducibility Principle
> (RFC0080-P1). Semiotically this is unremarkable — social meaning has
> always been carried by conventions no individual owns, which is
> Durkheim's social fact restated — and it addresses the formalization
> question of Issue RFC0080-I4: attributed meaning is a Collective State
> whose variable is interpretive, claimed and evidenced like any other,
> with this RFC supplying the account of why it is meaning and RFC 0080
> supplying the machinery of how it is claimed.

# Semantic Relationships

- A real-world **entity** is outside every model; it appears in the
  framework only through imputation.
- A **Persistent Identity** stands for exactly one entity, through an
  Existence Assertion; it **is realized by** one or more Identifiers.
- **Sameness** of identity across Identifiers is established by
  correspondence Governance Acts, never by string comparison.
- A **Semantic Interpretation** connects a Persistent Identity to a
  meaning within exactly one Semantic Domain; interpretations coexist
  without hierarchy.
- A **Designation** selects an interpretation or an identity for a stated
  purpose, and is a Governance Act (RFC0060-D2 species).

# Design Principles

## Principle RFC0015-P1 — Triadic Meaning Principle

> Meaning **shall** be modeled as a relation among entity, identity and
> interpreting domain. No Semantic Interpretation **shall** be treated as
> an intrinsic property of the entity.

## Principle RFC0015-P2 — Identity–Identifier Principle

> One Persistent Identity **may** be realized by many Identifiers.
> Sameness of identity **shall** be established by correspondence acts
> and **shall not** be inferred from identifier equality or descriptive
> similarity.

## Principle RFC0015-P3 — Designation Principle

> A Designation **shall** state its operational purpose and **shall**
> confer precedence only within it. No Designation **shall** establish
> semantic precedence among interpretations.

# Normative Requirements

> **Requirement RFC0015-R1 — Attributable interpretation**
>
> Every Semantic Interpretation shall be attributable to the Semantic
> Domain that makes it.

---

> **Requirement RFC0015-R2 — Identifier resolution**
>
> Every Identifier shall resolve to its Persistent Identity. Systems
> shall not treat identifier inequality as evidence of entity
> distinctness, nor identifier similarity as evidence of sameness.

---

> **Requirement RFC0015-R3 — Purposeful designation**
>
> A Designation shall identify its selecting Governance Act, its stated
> purpose, and the interpretation or identity selected. It shall be
> revisable in the manner of Governance Acts, with history preserved.

---

> **Requirement RFC0015-R4 — Repair without erasure**
>
> Correction of a reference failure — a misbinding, a duplicate, a failed
> imputation — shall be expressed by new records and Governance Acts.
> No repair shall erase the failed reference or its history.

# Examples

> **Example RFC0015-E1 — The triangle on a bike rack**
>
> The entity: steel in a park. The symbol: its Persistent Identity,
> asserted by the city's geospatial authority — the imputed base of the
> triangle made institutional. The interpretations: a point geometry
> (geospatial domain), an asset lifecycle record (asset domain), part of
> a place that families consider safe (population domain, collectively).
> None of the three is what the rack *really* is; each is answerable; and
> the Anchor Geometry among them is a Designation for the purpose of
> spatial joining, nothing more.

---

> **Example RFC0015-E2 — Migration without identity loss**
>
> The asset unit replaces its management system. Every database key
> changes; the new system's Identifiers share not one string with the
> old. Because identity is not identifier, the migration is a
> correspondence exercise: new Identifiers are bound to the same
> Persistent Identities, and ten years of maintenance history, citizen
> observations and state claims remain joined. The alternative —
> treating the re-key as new identities — would sever every cross-domain
> reference while changing nothing in the world.

---

> **Example RFC0015-E3 — A meaning shifts, the identity does not**
>
> A market square declines, and over a decade its attributed meaning
> among residents shifts from *everyday commons* to *place to avoid
> after dark*. The entity persists; the identity persists; what changes
> is an interpretation, recorded as superseding Collective State claims
> with their evidence. When regeneration reverses the shift, the claim
> history holds the entire arc — meaning as data, without the entity or
> its joins ever wavering.

# Planned Figures

> **Figure RFC0015-F1 (placeholder)**
>
> The triangle of reference, instantiated: entity, Persistent Identity
> and plural domain interpretations, with the Existence Assertion as the
> institutionalized base.
>
> *[Diagram to be inserted: fig-rfc0015-f1-triangle.svg]*

---

> **Figure RFC0015-F2 (placeholder)**
>
> One Persistent Identity, many Identifiers: correspondence acts
> establishing sameness across systems.
>
> *[Diagram to be inserted: fig-rfc0015-f2-identity-identifiers.svg]*

# Standards and Implementation Mappings

The following correspondences are informative.

| Framework concept | Correspondence (informative) |
|---|---|
| Triangle of reference | Ogden and Richards' semiotic triangle; Peirce's sign–object–interpretant triad |
| Identifier realization | Database keys, URIs, INSPIRE namespace + localId pairs realizing one identity |
| Correspondence of identities | `owl:sameAs` and skos mapping properties as implementation bindings for correspondence acts |
| Designation | Anchor Geometry (RFC0010-D4); primary identity of a reconciliation (RFC0060-R4) |
| Terminological grounding | ISO 19101 conceptual schema terminology (alignment per Issue RFC0015-I3) |

# Open Questions

> **Issue RFC0015-I1 — Temporal identity**
>
> When is a changed entity the same entity? A renovated bridge retains
> its identity; a demolished and rebuilt one arguably does not; the
> boundary between them is not semantic. The working position — identity
> criteria are themselves governance, exercised through assertion,
> withdrawal and succession acts — should be tested against RFC0010-I4
> and made explicit in a future revision.

---

> **Issue RFC0015-I2 — Meaning drift in vocabularies**
>
> Interpretations bind to external vocabularies (RFC0020-P2) whose terms
> themselves drift over decades. Whether the framework should say
> anything about vocabulary versioning as a meaning-stability concern,
> or leave it wholly to the vocabulary authorities, is open.

---

> **Issue RFC0015-I3 — ISO 19101 alignment**
>
> The terminology question raised in RFC 0002 — which terms require
> formal alignment with ISO 19101 — concentrates here, where the
> framework's use of *entity*, *identity* and *interpretation* meets the
> geographic information community's established vocabulary.

# References

- RFC 0000 — Introduction
- RFC 0001 — Design Principles
- RFC 0002 — Terminology and Naming Conventions
- RFC 0010 — Spatial Referent
- RFC 0020 — Semantic Domains
- RFC 0060 — Governance and Authority
- RFC 0080 — Population
- Editorial Style Guide
- C. K. Ogden and I. A. Richards, *The Meaning of Meaning*. London:
  Kegan Paul, 1923. (informative)
- C. S. Peirce, selected semiotic writings, in *Collected Papers of
  Charles Sanders Peirce*. Cambridge: Harvard University Press,
  1931–1958. (informative)
- ISO, "ISO 19101-1:2014 Geographic information — Reference model —
  Part 1: Fundamentals," Geneva: International Organization for
  Standardization. (informative)
