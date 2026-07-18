---
rfc: 0000
title: Introduction
status: Draft
category: Core
---

# Abstract

The Urban Digital Twin Semantic Framework defines a common semantic foundation for describing urban systems without prescribing a specific implementation technology, data model or software architecture. Its purpose is to clarify concepts, establish shared terminology, and provide a coherent framework through which independently governed information domains can interoperate.

Rather than replacing existing standards, the framework provides a semantic layer that explains how standards such as INSPIRE, OGC SensorThings, IDEF0, IFC and future domain models can coexist while preserving their own governance, terminology and conceptual integrity.

# Status of This Document

This document introduces the goals, scope and philosophy of the Urban Digital Twin Semantic Framework. Subsequent RFCs define the core concepts and their relationships in greater detail.

# Motivation

Cities are represented through numerous domain-specific information models, including geospatial data, infrastructure assets, operational activities, environmental observations and population-related information. Although these models frequently describe the same real-world places and objects, they often differ in vocabulary, assumptions and conceptual structure.

The framework addresses this challenge by defining a common semantic foundation rather than a common implementation.

# Purpose

The framework aims to:

- establish precise terminology for Urban Digital Twins;
- define relationships between core concepts;
- separate persistent identity from domain-specific meaning;
- support semantic interoperability between independently governed domains;
- remain independent of implementation technologies and information models.

# Design Philosophy

The framework is founded on four guiding principles:

1. **Identity is independent of meaning.**
2. **Semantic domains are orthogonal.**
3. **State is universal.**
4. **Governance establishes authority.**

# Scope

The framework specifies:

- semantic concepts;
- terminology;
- conceptual relationships;
- design principles;
- mappings to existing standards.

It does **not** specify:

- database schemas;
- APIs;
- exchange formats;
- ontologies;
- software architectures;
- implementation technologies.

# Relationship to Existing Standards

The framework complements rather than replaces existing standards. Standards such as INSPIRE, OGC SensorThings, IDEF0, IFC and CityGML continue to define their own domain semantics. This framework explains how those semantic models can coexist and interoperate.

# Structure of the RFC Series

- RFC 0001 – Design Principles
- RFC 0002 – Terminology Decisions
- RFC 0010 – Spatial Referent
- RFC 0015 – Identity, Meaning and Interpretation
- RFC 0020 – Semantic Domains
- RFC 0030 – State
- RFC 0040 – Observation
- RFC 0050 – Activity
- RFC 0060 – Governance and Authority
- RFC 0070 – Semantic Interoperability
- RFC 0080 – Population

# Intended Audience

- Urban Digital Twin architects
- Geospatial professionals
- Information architects
- Systems engineers
- Standards developers
- Researchers

# Conformance

Conformance is achieved by preserving the semantic intent of the concepts and relationships defined in the RFC series rather than by adopting any specific technology.

# Open Questions

This introduction will evolve as subsequent RFCs mature.

# References

Normative and informative references are defined within the individual RFCs.
