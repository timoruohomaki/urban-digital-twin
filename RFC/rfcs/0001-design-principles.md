---
rfc: 0001
title: Design Principles
status: Draft 0.2
category: Core
---

# Abstract

This RFC establishes the normative design principles of the Urban Digital Twin
Semantic Framework. These principles define the semantic and institutional
foundations upon which all subsequent RFCs are based.

# Status of This Document

This document is normative. Subsequent RFCs shall conform to these principles
unless an exception is explicitly justified.

# Motivation

Urban Digital Twins operate in highly distributed environments where information
is created and governed by multiple autonomous authorities. Rather than defining
a canonical information model, this framework establishes principles that enable
independent semantic domains to interoperate while preserving their autonomy.

# Philosophy

The framework distinguishes between:

- Reality
- Persistent Identity
- Semantic Interpretation
- Information Models
- Implementations

Concepts are defined independently of technologies and implementation standards.

---

# Semantic Axioms

## Principle RFC0001-P1 — Identity Independence Principle

> A persistent identity **shall** be independent of any semantic interpretation.

### Consequences

- Identity precedes semantic interpretation.
- Semantic meaning may evolve without changing identity.
- Multiple semantic domains may reference the same entity.

> **Definition RFC0001-D1 — Persistent Identity**
>
> A Persistent Identity is the stable reference through which semantic domains
> associate meaning with the same real-world entity.

---

## Principle RFC0001-P2 — Orthogonal Semantic Domains Principle

> Semantic domains **shall** remain conceptually independent.

### Consequences

- No canonical semantic domain exists.
- Domains evolve independently.
- Interoperability is achieved through shared identity.

---

# System Axioms

## Principle RFC0001-P3 — Universal State Principle

> Every semantic domain **shall** define state for the entities within its scope.

### Consequences

- State is independent of domain type.
- Every autonomous domain manages its own state.
- State models may differ between domains.

---

## Principle RFC0001-P4 — Governance Authority Principle

> The authority of semantic interpretations **shall** be established through governance rather than semantics.

### Consequences

- The framework does not determine authoritative interpretations.
- Multiple authoritative sources may coexist.
- Governance is external to the semantic model.

---

## Principle RFC0001-P5 — Institutional Autonomy Principle

> Every governing authority **shall** remain semantically autonomous within its own area of responsibility.

### Rationale

Urban Digital Twins are developed within ecosystems composed of multiple
governing authorities. Each authority maintains responsibility for its own
decisions, information assets, terminology, processes and technology.

The framework therefore assumes institutional autonomy as the normal operating
condition.

### Consequences

- Semantic domains evolve independently.
- Information systems may be independently procured and operated.
- Technology choices remain local decisions.
- Authorities retain ownership of their own semantics.
- Interoperability is achieved through coordination rather than semantic standardization.
- Shared identity provides the foundation for cross-domain interoperability.

> **Note RFC0001-N2 — Municipal Governance**
>
> Municipal governments are often presented externally as single organizations.
> In practice they comprise multiple governing authorities with distinct
> responsibilities, governance arrangements, information systems and semantic
> models. The framework therefore assumes institutional autonomy rather than
> centralized semantic governance.

# Architectural Consequences

> **Table RFC0001-T1 (placeholder)**
>
> Summary of design principles and their architectural consequences.
>
> *[Table to be inserted.]*

# Relationship to Existing Standards

These principles are technology-independent.

Mappings to standards such as INSPIRE, IFC, CityGML, OGC API standards,
SensorThings API and ISO TC 211 are informative rather than normative.

# Planned Figures

> **Figure RFC0001-F1 (placeholder)**
>
> Reality, Persistent Identity and Semantic Interpretation.
>
> *[Diagram to be inserted.]*

---

> **Figure RFC0001-F2 (placeholder)**
>
> Orthogonal Semantic Domains sharing a common Spatial Referent.
>
> *[Diagram to be inserted.]*

---

> **Figure RFC0001-F3 (placeholder)**
>
> Governance, Authority and Semantic Interpretation.
>
> *[Diagram to be inserted.]*

---

> **Figure RFC0001-F4 (placeholder)**
>
> Institutional Autonomy within a Municipal Ecosystem.
>
> *[Diagram to be inserted.]*

# Open Questions

- Should temporal identity become an explicit principle?
- Should institutional autonomy be generalized beyond public-sector governance?
- Should additional system axioms emerge from later RFCs?

# References

- RFC 0000 — Introduction
- Editorial Style Guide
