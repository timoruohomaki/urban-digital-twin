---
rfc: 0060
title: Governance and Authority
status: Draft 0.1
category: Core
---

# Abstract

This RFC defines how authority works in the Urban Digital Twin Semantic
Framework. Authority is established through governance, not semantics
(RFC0001-P4): nothing is authoritative by default, by technical possession
or by hosting arrangement. The instrument of authority is the Governance
Act — an identifiable, citable institutional act by a Governing Authority —
and the scattered governance references of earlier RFCs (asserting a
referent, designating an Anchor Geometry, declaring a state, establishing a
Control, accepting responsibility in a handoff) are unified as its species.

Coordination across authorities rests on the Shared Contract: an explicit,
minimal agreement on the elements treated as shared — at minimum, Spatial
Referent identities — while everything else remains under autonomous
governance. This RFC resolves referent minting and reconciliation (Issue
RFC0010-I2) and cross-authority processes (Issue RFC0050-I2).

# Status of This Document

This document is normative. It derives from the principles established in
RFC 0001 — particularly the Governance Authority Principle (RFC0001-P4) and
the Institutional Autonomy Principle (RFC0001-P5) — and uses the
terminology of RFC 0002, elaborating the Governing Authority (RFC0002-D4)
and Institutional Autonomy (RFC0002-D5).

# Motivation

Every preceding RFC leans on governance at its load-bearing points. The
Spatial Referent exists because an authority asserts it (RFC0010-D2) and
joins spatially through a governance-designated Anchor Geometry
(RFC0010-D4). Declared State Claims identify the governance act that
establishes them (RFC0030-R3). Controls, including Intended State,
condition activities on institutional ground (RFC 0050). What none of those
RFCs defines is the governance machinery itself: who may act, what an act
is, how acts are cited, and how independently governed authorities
coordinate without surrendering autonomy.

The institutional reality this must fit is plain: a municipality is
presented externally as one organization but comprises many governing
authorities with distinct responsibilities, systems and semantics (Note
RFC0001-N2). The framework's answer is not to unify them — that would
violate RFC0001-P5 and repeat the centralized-platform mistake — but to
make the minimum they must share explicit, and everything else visibly
autonomous. The cost of that minimum is institutional coordination, not
technology; it is the single most consequential agreement an urban data
ecosystem makes.

# Terminology

## Definition

> **Definition RFC0060-D1 — Area of Responsibility**
>
> The declared scope within which a Governing Authority governs: the
> Semantic Domains it owns, the State Subjects it manages, and the
> territorial or thematic extent of its mandate.

---

> **Definition RFC0060-D2 — Governance Act**
>
> An identifiable institutional act by which a Governing Authority
> establishes, changes or withdraws a normative arrangement. Species
> include: asserting or withdrawing a Spatial Referent (RFC 0010);
> designating, such as an Anchor Geometry (RFC0010-D4) or a primary
> identity (RFC0060-R4); declaring a State Claim (RFC0030-R3);
> establishing a Control or Intended State (RFC 0050); accepting
> responsibility in a handoff (RFC0060-R7); and delegating (RFC0060-D4).

---

> **Definition RFC0060-D3 — Shared Contract**
>
> An explicit agreement among two or more Governing Authorities
> establishing the elements they treat as shared. All elements not named in
> a Shared Contract remain under autonomous governance.

---

> **Definition RFC0060-D4 — Delegation**
>
> A Governance Act by which an authority grants another party the capacity
> to perform specified Governance Acts within a defined scope. Delegated
> acts remain attributable both to the performing delegate and to the
> delegating authority.

## Scope

This RFC specifies:

- the Governance Act and its species;
- Areas of Responsibility and the attribution of acts;
- the minting and reconciliation of Spatial Referents;
- the Shared Contract as the coordination instrument;
- Delegation;
- responsibility handoff in cross-authority Processes.

## Not in Scope

This RFC does not specify:

- the internal organization, mandates or legal form of any authority;
- evidence methodology or the assessment of claims (Note RFC0080-N9,
  Note RFC0040-N6);
- dispute resolution procedures (see Issue RFC0060-I1);
- registry technology, identifier syntax or policy languages;
- competence and staffing of governance roles.

# Core Concepts

## Authority is enacted, not possessed

Holding data confers no authority over its meaning; operating a system
confers no authority over the domain it serves. Authority attaches to
Governance Acts performed by an authority within its Area of
Responsibility, and every downstream construct that relies on authority —
a declared claim, a designation, a control — cites the act it relies on.
"System of record" is thus a governance designation, revocable and
citable, never a technical fact.

> **Note RFC0060-N1 — Coexistence without hierarchy**
>
> Per RFC0001-P4, multiple authoritative interpretations coexist. The land
> registry's parcel geometry and the city model's building geometry are
> both authoritative — within their respective domains and purposes. Where
> a single answer is operationally required, governance designates one for
> the purpose, and the designation confers operational precedence only.
> This is the recurring figure of the series (Note RFC0030-N2) at its
> governance root: Anchor Geometry (RFC0010-R6) and the primary identity
> of a reconciliation (RFC0060-R4) are its instances.

## Minting and reconciling referents

Any Governing Authority may assert Spatial Referents within its Area of
Responsibility, and the asserting authority carries the persistence
obligations of RFC0010-R4 and RFC0010-R5. This resolves the minting half
of Issue RFC0010-I2.

Duplicates are the normal consequence of autonomy: two authorities will
sometimes assert referents for the same real-world entity. Reconciliation
is not deletion — deleting an identity would break every reference under
the other authority's governance. Reconciliation is a Governance Act
establishing a correspondence between the referents, optionally
designating one as primary for joining purposes. Both identities remain
resolvable; the non-primary resolves through the correspondence. The
primary designation is operational precedence in the sense of Note
RFC0060-N1, not a judgement that one authority's assertion was wrong.

## The Shared Contract

Interoperability across authorities is achieved by agreement on a minimal
set of shared elements, not by semantic standardization (RFC0001-P5). The
floor of every Shared Contract is identity: the participating authorities
treat Spatial Referent identities as the common join element, using
consistent identifiers when referencing the same real-world entity. Above
that floor, a contract may name further shared elements — a resolution
rule for subject binding, a designated Anchor Geometry source, a shared
vocabulary binding — each an explicit, deliberate addition.

The contract is deliberately institutional rather than technical: it
requires no schema changes, no data migration and no platform. Its
analogue in the data spaces world is connector registration — the act by
which a participant joins a federation under agreed terms while retaining
sovereignty over what it exposes.

> **Note RFC0060-N2 — The concrete minimal contract**
>
> In a typical municipality the minimal contract has three parties: the
> geospatial authority asserting referents and designating Anchor
> Geometries, the asset authority binding lifecycle records to those
> identities, and the civic reporting operator resolving citizen
> observations to them. The agreement that these three use consistent
> referent identities for the same physical objects is the entire entry
> cost of the urban data space. Everything else — their schemas, their
> systems, their vocabularies — remains their own.

> **Note RFC0060-N3 — Accountable domains**
>
> The federated-accountability reading of data mesh applies here: a
> Semantic Domain under a Governing Authority is an ownership boundary
> with accountability for quality, integrity and meaning — not a folder,
> not a dataset. The Shared Contract is the interface between such
> accountable domains; the framework deliberately gives it no more content
> than the interface needs.

## Delegation

Governance scales by delegation. The resolution of subject bindings
"under rules owned by the resolving authority" (RFC 0040) is typically a
delegation: the geospatial authority delegates resolution against its
Anchor Geometries to the reporting system's operator, within a scope and
revocably. Delegation keeps acts attributable — the delegate performs,
the delegating authority answers — and keeps the framework honest about
who established what.

## Handoff in cross-authority processes

A Process may span authorities: a utility's cable repair inside a city's
street works. The semantic content of the handoff is threefold.
Responsibility passes at an Activity boundary through a Governance Act of
acceptance; within each segment, the Controls of the responsible
authority apply; and the State Subject's referent identity persists
across the handoff — the join key is precisely what survives the
organizational seam. Each authority's own Controls, including its
Intended States, are evaluated against its own segment; a control of one
authority does not silently govern another's work. This resolves Issue
RFC0050-I2 at the semantic level; procedural detail remains institutional.

# Semantic Relationships

A Governing Authority:

- **declares** an Area of Responsibility;
- **governs** Semantic Domains within it (RFC0002-D2);
- **performs** Governance Acts, directly or through Delegation;
- **participates in** Shared Contracts.

A Governance Act:

- **is performed by** exactly one Governing Authority, possibly through a
  delegate;
- **is identifiable and citable**, so that declared State Claims,
  designations, Controls and handoffs can reference it;
- **may be withdrawn or superseded** by a later act of the same or a
  mandated authority, with history preserved in the manner of RFC0030-P1.

A Shared Contract **binds** two or more Governing Authorities,
**enumerates** its shared elements explicitly, and **implies nothing**
about elements it does not name.

# Design Principles

## Principle RFC0060-P1 — Minimal Contract Principle

> A Shared Contract **shall** be minimal and explicit. Participation
> **shall not** require changes to a participant's internal semantics,
> systems or vocabularies beyond the shared elements named.

## Principle RFC0060-P2 — Explicit Authority Principle

> Authority **shall** be traceable to identifiable Governance Acts within
> a declared Area of Responsibility. No interpretation is authoritative by
> default, by technical possession, or by hosting arrangement.

# Normative Requirements

> **Requirement RFC0060-R1 — Attributable, citable acts**
>
> Every Governance Act shall be attributable to a Governing Authority and
> identifiable such that dependent constructs — declared State Claims,
> designations, Controls, handoffs — can cite it.

---

> **Requirement RFC0060-R2 — Declared responsibility**
>
> A Governing Authority shall declare its Area of Responsibility. An
> assertion outside a declared area carries no authority by virtue of
> being asserted.

---

> **Requirement RFC0060-R3 — Minting**
>
> A Governing Authority may assert Spatial Referents within its Area of
> Responsibility. The asserting authority shall carry the persistence and
> lifecycle obligations of RFC0010-R4 and RFC0010-R5.

---

> **Requirement RFC0060-R4 — Reconciliation without deletion**
>
> Duplicate referents for one real-world entity shall be reconciled by a
> Governance Act establishing their correspondence. A primary identity may
> be designated for joining purposes; all reconciled identities shall
> remain resolvable, and none shall be deleted.

---

> **Requirement RFC0060-R5 — Explicit shared elements**
>
> The elements treated as shared among authorities shall be enumerated in
> a Shared Contract. Elements not enumerated remain autonomous, and no
> shared element shall be introduced implicitly through technical
> integration.

---

> **Requirement RFC0060-R6 — Scoped, revocable delegation**
>
> A Delegation shall be explicit, scoped and revocable. Acts performed
> under delegation shall remain attributable to both the delegate and the
> delegating authority.

---

> **Requirement RFC0060-R7 — Handoff**
>
> In a Process spanning Governing Authorities, transfer of responsibility
> shall be expressed as a Governance Act of acceptance at an Activity
> boundary. Within each segment the Controls of the responsible authority
> shall apply, and the State Subjects' referent identities shall persist
> across the handoff.

# Examples

> **Example RFC0060-E1 — Three parties, one contract**
>
> A city's geospatial unit asserts referents for parks and street
> furniture and designates Anchor Geometries. The asset unit binds
> lifecycle records to those identities. The civic reporting operator
> resolves citizen observations against the Anchor Geometries — under a
> delegation from the geospatial unit that names the resolution rule and
> its scope. The Shared Contract enumerates exactly two shared elements:
> the referent identities and the resolution delegation. The asset unit's
> condition grades, the operator's category taxonomy and the geospatial
> unit's data model never enter the contract, and none of the three can
> impose a schema on another.

---

> **Example RFC0060-E2 — One bridge, two authorities**
>
> A bridge is asserted as a referent by the street authority (it carries a
> road) and by the waterways authority (it crosses a channel). Both
> assertions are legitimate acts within declared areas. Reconciliation
> establishes the correspondence; for joining, the street authority's
> identity is designated primary because the asset register keys on it.
> The waterways authority's identity remains resolvable through the
> correspondence, and its inspection observations join the same physical
> bridge without either authority renumbering anything.

---

> **Example RFC0060-E3 — Handoff in a street repair**
>
> A citizen reports a dark street; the city's process classifies the fault
> to a cable owned by the utility. At the activity boundary the utility
> performs an acceptance act; its safety and work-permit Controls govern
> the excavation segment, while the city's response-time Intended State
> continues to apply only to the city's own segments. The streetlight's
> referent identity persists throughout, so the citizen's original
> observation, the utility's work records and the closing state transition
> join without any shared system between city and utility.

# Planned Figures

> **Figure RFC0060-F1 (placeholder)**
>
> Governing Authorities with Areas of Responsibility, joined by a Shared
> Contract enumerating referent identities as the shared floor.
>
> *[Diagram to be inserted: fig-rfc0060-f1-shared-contract.svg]*

---

> **Figure RFC0060-F2 (placeholder)**
>
> Reconciliation of duplicate referents: correspondence act, primary
> designation for joining, both identities resolvable.
>
> *[Diagram to be inserted: fig-rfc0060-f2-reconciliation.svg]*

---

> **Figure RFC0060-F3 (placeholder)**
>
> Cross-authority handoff: acceptance acts at Activity boundaries,
> per-segment Controls, persistent referent identity.
>
> *[Diagram to be inserted: fig-rfc0060-f3-handoff.svg]*

# Standards and Implementation Mappings

The following correspondences are informative.

| Framework concept | Correspondence (informative) |
|---|---|
| Shared Contract | IDS connector registration and usage contracts; GAIA-X trust framework participation |
| Governing Authority / accountable domain | Data mesh domain ownership with federated accountability |
| Minting and persistence obligations | INSPIRE External Object Identifier governance: namespace ownership, identifier persistence mandates |
| Governance Act species | Registry decisions, administrative rulings, designation records, delegation instruments |
| Handoff | Inter-organizational service agreements; work-order transfer with acceptance records |
| Public-sector governance context | ISO 55011 (public policy for asset management); ISO 55013 (data as an asset, data lifecycle governance) |

# Open Questions

> **Issue RFC0060-I1 — Disputes**
>
> When two authorities claim overlapping Areas of Responsibility — not
> duplicate referents, but contested mandates — semantics cannot resolve
> the contest. Should the framework make disputes representable (a visible
> seam: contested, unresolved) rather than forcing premature designation?

---

> **Issue RFC0060-I2 — Non-institutional actors**
>
> Community groups, research projects and volunteered geographic
> information hold no municipal mandate but produce durable, valuable
> assertions. Can such actors hold governance standing directly, or only
> through delegation from an institutional authority? The answer shapes
> how citizen science enters the twin.

---

> **Issue RFC0060-I3 — Governance of the contract**
>
> The Shared Contract itself needs governance: how it is amended, how a
> participant joins or leaves, and how changes avoid breaking joins that
> earlier terms enabled. Whether contract evolution needs framework
> treatment or remains purely institutional is open.

---

> **Issue RFC0060-I4 — Machine-actionable acts**
>
> Governance Acts are citable; should they also be machine-readable, so
> that delegation scopes, control applicability and contract terms can be
> evaluated computationally? This leans toward implementation, but the
> boundary between citable and computable may deserve a semantic
> statement.

# References

- RFC 0000 — Introduction
- RFC 0001 — Design Principles
- RFC 0002 — Terminology and Naming Conventions
- RFC 0010 — Spatial Referent
- RFC 0030 — State
- RFC 0040 — Observation
- RFC 0050 — Activity
- Editorial Style Guide
- International Data Spaces Association, "IDS Reference Architecture
  Model 4.0," 2022. (informative)
- Z. Dehghani, *Data Mesh: Delivering Data-Driven Value at Scale*.
  Sebastopol: O'Reilly Media, 2022. (informative)
- European Commission, Directive 2007/2/EC (INSPIRE), 2007. (informative)
- ISO, "ISO 55011" and "ISO 55013," asset management guidance standards,
  2024. (informative)
