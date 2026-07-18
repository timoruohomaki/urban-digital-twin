# Editorial Style Guide

**Urban Digital Twin Semantic Framework**

Version: Draft 0.1

---

# 1. Purpose

This document defines the editorial conventions used throughout the RFC series. Its objectives are to:

- maintain consistent terminology;
- provide stable identifiers for normative content;
- separate normative and informative text;
- simplify cross-referencing;
- support future publication as online documentation and formal specifications.

---

# 2. Document Structure

Each RFC should generally follow this structure:

1. Abstract
2. Status of This Document
3. Motivation
4. Scope
5. Terminology
6. Definitions
7. Normative Requirements
8. Design Discussion
9. Examples
10. Relationship to Existing Standards
11. References

Individual RFCs may add sections when justified.

---

# 3. RFC Numbering

RFC numbers are permanent.

Example:

- RFC 0000 – Introduction
- RFC 0001 – Design Principles
- RFC 0010 – Spatial Referent

RFC numbers shall never be reused.

---

# 4. Identifier Convention

Every reusable element receives a globally unique identifier.

| Element | Identifier | Example |
|---------|------------|---------|
| Principle | RFC0001-P1 | Identity Independence Principle |
| Definition | RFC0010-D1 | Spatial Referent |
| Requirement | RFC0010-R1 | Persistent Identity |
| Figure | RFC0001-F1 | Overall Conceptual Model |
| Table | RFC0001-T1 | Design Principles |
| Example | RFC0010-E1 | Municipal Park |
| Note | RFC0010-N1 | Persistence |
| Issue | RFC0010-I1 | Open Question |

Identifiers remain stable even if sections move.

---

# 5. Normative Language

The framework adopts the terminology defined by RFC 2119.

- **shall** — mandatory
- **shall not** — prohibited
- **should** — recommended
- **should not** — discouraged
- **may** — optional

Normative requirements shall be clearly distinguishable from explanatory text.

---

# 6. Normative vs Informative Content

## Normative

- Principles
- Definitions
- Requirements
- Rules

## Informative

- Notes
- Examples
- Discussion
- Rationale
- Background

---

# 7. Figures

Figures shall use permanent identifiers.

Example:

> **Figure RFC0001-F1 (placeholder)**  
> Relationship between Reality, Identity and Semantic Interpretation.  
> *[Diagram to be inserted.]*

Recommended filenames:

```
fig-rfc0001-f1-overall-concept.svg
fig-rfc0001-f2-semantic-domains.svg
```

---

# 8. Tables

Tables use the same convention.

Example:

> **Table RFC0001-T1**  
> Summary of Design Principles.

---

# 9. Definitions

Definitions should follow a standard format.

> **Definition RFC0010-D1 — Spatial Referent**

Definitions should be concise, technology-independent and avoid examples unless essential.

---

# 10. Examples

Examples illustrate concepts but never modify definitions.

> **Example RFC0010-E1**

Examples should represent realistic Urban Digital Twin scenarios.

---

# 11. Notes

Notes clarify intent but are not normative.

> **Note RFC0010-N1**

Notes should explain interpretation, assumptions or relationships.

---

# 12. Editorial Conventions

- Use sentence case for headings.
- Capitalize defined concepts (e.g. Spatial Referent, Semantic Domain, Activity) when used in their formal meaning.
- Use present tense.
- Prefer active voice.
- Avoid implementation-specific terminology unless discussing mappings.
- Keep definitions independent of particular standards or technologies.

---

# 13. Cross References

Cross references should cite identifiers rather than section numbers.

Preferred:

- Principle RFC0001-P2
- Definition RFC0010-D1
- Figure RFC0001-F2

Avoid references such as "see Section 4.3" where possible.

---

# 14. Living Document

This style guide is expected to evolve alongside the RFC series. Changes should improve consistency without invalidating existing identifiers.
