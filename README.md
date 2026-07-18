# Urban Digital Twin

Working documents on standards-based urban digital twins: a semantic
framework published as an RFC series, with data analyses and reference
implementation notes to follow.

## About

This repository collects public working documents from an ongoing research
effort on the Urban Digital Twin (UDT) as a socio-technical, standards-based
data ecosystem. The central claim, developed across the documents here, is
that a functional urban digital twin is **not a platform to be built but a
data space to be governed**: independently governed municipal domains —
geospatial information, dynamic observations, asset management, and the
population — interoperate through a shared, minimal join key anchored in the
OGC geospatial feature, while everything else remains under each domain's
own governance.

The work builds on open standards throughout: OGC API Features, OGC
SensorThings API, the OGC Points of Interest conceptual model, INSPIRE data
products, ISO 55000 asset management, ISO 19157 data quality, and IDEF0
functional modeling.

## Publications

### UDT Semantic Framework (RFC series) — early draft, comments welcome

An implementation-independent semantic framework for urban digital twins,
written as a series of RFC-style documents. The framework defines a small
set of interlocking concepts — the Spatial Referent as an existence-only
identity anchor, Semantic Domains as autonomous interpretation owners,
Observations as immutable evidence, State as revisable claims, Activities
as the processes that close the evidence loop, and Governance as the source
of all authority — and shows how semantic interoperability follows from
them without shared schemas or centralized models.

| RFC | Title | Status |
|-----|-------|--------|
| 0000 | Introduction | Draft |
| 0001 | Design Principles | Draft 0.2 |
| 0002 | Terminology and Naming Conventions | Draft 0.1 |
| 0010 | Spatial Referent | Draft 0.2 |
| 0015 | Identity, Meaning and Interpretation | Draft 0.1 |
| 0020 | Semantic Domains | Draft 0.1 |
| 0030 | State | Draft 0.2 |
| 0040 | Observation | Draft 0.4 |
| 0050 | Activity | Draft 0.1 |
| 0060 | Governance and Authority | Draft 0.1 |
| 0070 | Semantic Interoperability | Draft 0.1 |
| 0080 | Population | Draft 0.3 |

Alongside the RFCs, the `mappings/` folder holds non-normative mappings to
existing standards (OGC SensorThings, IDEF0, INSPIRE), and each RFC ends
with an explicit list of open questions.

The series is at an early stage and is published now precisely to gather
comments, criticism and ideas while the concepts are still moving.

### Planned additions

- **Boston Open311 analysis** — profiling of roughly 1.4 million service
  requests (2019–2023): the stable three-tier service taxonomy, geospatial
  coverage and its anomalies, SLA structures and their gaps. This dataset
  informs several design decisions in the RFC series, including the
  function-stability principle of RFC 0050.
- **Spatial data lake** — notes on the reference implementation: an ELT
  pipeline over PostGIS and pygeoapi serving INSPIRE-aligned OGC API
  Features, with R-based analysis and enriched document views.

## How to comment

Open a GitHub issue — disagreements, counterexamples and pointers to prior
art are all welcome. Every normative element in the RFC series carries a
permanent identifier (definitions `RFC0010-D1`, principles `RFC0001-P2`,
requirements `RFC0040-R5`, notes, examples and open issues alike), so the
most useful form of comment cites the identifier it concerns, for example:

> RFC0030-N1: the supersession criterion fails for X because…

RFC numbers and element identifiers are never reused, so references stay
stable as the drafts evolve. The editorial conventions are described in
`rfcs/editorial-style-guide.md`.

## Background

The conceptual starting points are documented in earlier published work:

- T. Ruohomäki, E. Airaksinen, M. Martikka, O. Kesäniemi, P. Huuska and
  J. Suomisto, "Smart City Platform Enabling Digital Twin," *Proc. IEEE
  International Conference on Intelligent Systems (IS 2018)*, Funchal,
  2018.
- T. Ruohomäki, A. Andra and K. Raivio, "Defining Data-Driven Analytical
  Methods on Improving Energy-Efficiency in Apartment Buildings,"
  *Engineering Proceedings*, vol. 2, no. 68, 2020.

Further conference publications developing the data space argument are in
preparation.

## Related projects

- [open311-to-Go](https://github.com/timoruohomaki/open311-to-Go) — Go
  implementation of the Open311 API with feature identifiers for linking
  service requests to OGC features.
- [idefinity](https://github.com/timoruohomaki/idefinity) — Xojo desktop
  IDEF0 modelling tool exporting machine-readable process models.

## Author

Timo Ruohomäki — LUT University, Lappeenranta, Finland.

## License

To be added.
