# OGC Points of Interest

Status: Draft. Non-normative.

This mapping relates the OGC Points of Interest Conceptual Model Standard
1.0 (OGC 21-049) to the concepts of the Urban Digital Twin Semantic
Framework, principally RFC 0010 (Spatial Referent), with connections to
RFC 0015 (Identity, Meaning and Interpretation), RFC 0020 (Semantic
Domains) and RFC 0030 (State). See also Note RFC0010-N6, which motivates
this mapping.

The POI model admits a POI "as simple as a set of coordinates and an
identifier" — the closest published standard form to an existence-minimal
Spatial Referent. Several of its design choices align with framework
machinery arrived at independently; the divergences are equally
instructive.

## Element mapping

| POI element | Framework concept | Notes |
|---|---|---|
| `featureID` (GenericName) | Identifier (RFC0015-D1) realizing a Persistent Identity | The local identifier |
| Additional identifiers (ScopedName) | Further Identifiers of the same Persistent Identity | Sameness is established by correspondence (RFC0060-R4), never by string equality (RFC0015-P2) |
| Geometry (Point, LineString, Polygon per ISO 19107) | Geometric Interpretation (RFC0010-D3); Anchor Geometry candidate (RFC0010-D4) | The minimal POI — coordinates plus identifier — is the minimal referent carrier |
| `creationDate` / `terminationDate` | Record lifecycle: the time claims are made and retired | Database time, matching the claim-time half of RFC 0030's two-times discipline |
| `validFrom` / `validTo` | Existence Assertion lifecycle (RFC0010-D2, RFC0010-R5) | Real-world time, matching the condition-time half |
| `hasFeatureOfInterest` association | Relationships to other Spatial Referents | Domain-owned interpretations per Note RFC0010-N4; composition candidates |
| `name`, `description`, `contactInfo` | Descriptive content owned by interpreting domains | Not part of the referent itself (RFC0010-R2); a designated display name would be a Designation (RFC0015-D2) |
| Keywords, categories | Classification Facets bound to vocabularies (RFC0020-D2, RFC0020-R4) | Bind externally rather than mint (RFC0020-P2) |
| `POI_Payload` (`usesSchema`, `hasDefinition`) | Domain Extension (RFC0020-D4) | The payload's required external schema reference is the provenance discipline of RFC0020-R5 in standard form |

## Reading the POI as a minimal referent carrier

Read through the framework, a published POI carries a Spatial Referent's
identity plus one Geometric Interpretation and an open set of
domain-extension payloads. This makes the POI model a natural publication
form for referents whose authoritative geometry is coarse or still
evolving — the planned feature published as a point before the as-built
polygon exists (Example RFC0010-E3) — and for referents whose interest to
consumers precedes any richer representation.

## Notable divergences

- The POI bundles identity, location and description into one construct;
  the framework factors identity into the Spatial Referent and everything
  else into Semantic Interpretations. The same factoring caveat applies as
  for the OGC feature (Note RFC0010-N5): the POI is a minimal *carrier*,
  not the pure concept.
- POI geometry is restricted to Point, LineString and Polygon. The
  framework places no restriction on Geometric Interpretations; richer
  representation is reached by reference (RFC0070-R3), which the POI
  supports through payload references rather than through its geometry
  property.
- The POI model has no evidence or state machinery. Statements about the
  condition, occupancy or perception of the thing a POI stands for are
  Observations (RFC 0040) and State Claims (RFC 0030) referencing the
  POI's identity — they are not POI properties, and modeling them as
  payload attributes would forfeit the supersession and provenance
  disciplines.
