---
rfc: 0002
title: Terminology and Naming Conventions
status: Draft 0.1
category: Core
---

# Abstract

This RFC establishes the normative terminology of the Urban Digital Twin
Semantic Framework. Its purpose is to ensure that concepts are used
consistently throughout the RFC series and that implementation-specific
terminology does not influence the conceptual model.

# Status of This Document

This document is normative. Definitions contained in this RFC shall be used
consistently by subsequent RFCs unless explicitly superseded.

# Motivation

Interoperability depends not only on exchanging information but also on
sharing a common understanding of concepts. Many terms used in Urban Digital
Twin initiatives have different meanings across standards and disciplines.

This RFC defines the terminology adopted by this framework.

# Relationship to RFC 0001

This RFC derives from:

- RFC0001-P1 — Identity Independence Principle
- RFC0001-P2 — Orthogonal Semantic Domains Principle
- RFC0001-P5 — Institutional Autonomy Principle

The terminology defined here supports semantic interoperability while
respecting institutional autonomy.

# Terminology Principles

## Principle RFC0002-P1 — Technology Independence

Concepts shall be defined independently of implementation technologies.

Examples of implementations include:

- RDF
- UML
- JSON
- Relational databases
- OGC APIs

These are realizations of concepts, not the concepts themselves.

---

## Principle RFC0002-P2 — Stable Terminology

Defined terms shall retain a single meaning throughout the specification.

New RFCs shall extend terminology rather than redefine existing concepts.

# Core Terminology

> **Definition RFC0002-D1 — Concept**
>
> An abstract unit of meaning defined by this framework.

---

> **Definition RFC0002-D2 — Semantic Domain**
>
> A coherent body of concepts, relationships and state governed by a
> particular perspective or authority.

---

> **Definition RFC0002-D3 — Semantic Interpretation**
>
> The meaning assigned to a Persistent Identity by a Semantic Domain.

---

> **Definition RFC0002-D4 — Governing Authority**
>
> An institution or organizational unit responsible for governing a semantic
> domain within its area of responsibility.

---

> **Definition RFC0002-D5 — Institutional Autonomy**
>
> The ability of a Governing Authority to manage its own semantics,
> information assets, processes and technologies independently of other
> governing authorities.

# Naming Conventions

The framework distinguishes between conceptual entities and their
implementations.

Examples:

| Concept | Possible implementation |
|---------|--------------------------|
| Persistent Identity | UUID, URI, primary key |
| Semantic Domain | Ontology, schema, API |
| State | Database record, event stream |
| Spatial Referent | Feature, object, entity |

Implementation examples are informative only.

# Preferred Terminology

| Preferred | Avoid where a conceptual term is intended |
|------------|-------------------------------------------|
| Semantic Domain | Dataset, database |
| Persistent Identity | Identifier field |
| Governing Authority | System owner |
| Spatial Referent | Feature (unless referring to a specific standard) |
| Semantic Interpretation | Label, attribute value |

# Editorial Guidance

Defined concepts are capitalized when used in their normative sense.

Example:

- Spatial Referent (defined concept)
- spatial referent (generic usage)

# Planned Figures

> **Figure RFC0002-F1 (placeholder)**

Concepts versus implementations.

*[Diagram to be inserted.]*

---

> **Figure RFC0002-F2 (placeholder)**

Relationship between Governing Authority, Semantic Domain and Semantic Interpretation.

*[Diagram to be inserted.]*

# Planned Tables

> **Table RFC0002-T1 (placeholder)**

Glossary of normative terms.

# Open Questions

- Which terms require formal alignment with ISO 19101 terminology?
- Should "Spatial Referent" be reserved exclusively for this framework?
- Should a machine-readable glossary accompany the RFC series?

# References

- RFC 0000 — Introduction
- RFC 0001 — Design Principles
- Editorial Style Guide
