---
rfc: 0080
title: Population
status: Draft 0.3
category: Core
---

# Abstract

This RFC defines the population dimension of the Urban Digital Twin Semantic
Framework. The population domain interprets a Spatial Referent as a Place:
the entity as experienced, used and given meaning by people. The population
dimension itself is expressed as state, not as an entity: Collective State —
temporally qualified properties such as attributed meaning, perceived safety
and perceived comfort — claimed for a Place, or for a configuration of
Places, with respect to a membership criterion.

No population entity is modeled. The subject of interest is the place and the
patterns and changes of its social dimension; the population is the live
snapshot those states describe. Individual-level inputs — citizen reports,
survey responses, sensor-mediated signals — are observations in the sense of
RFC 0040 and enter the population domain only as evidence from which
Collective State is estimated through analysis capable of identifying
patterns and changes, never as terms of a sum.

# Status of This Document

This document is normative. It derives from the principles established in
RFC 0001, uses the terminology of RFC 0002, and builds on the Spatial
Referent defined in RFC 0010. Draft 0.2 resolves the entity-versus-state
question left open in Draft 0.1 (see Note RFC0080-N6). Draft 0.3 resolves
the evidence legitimacy question (see Note RFC0080-N9).

# Motivation

An Urban Digital Twin without a population dimension is, in Batty's phrase, a
digital version of the architect's wooden model: a representation of the
physical city that does not attempt to involve the people whose city it is.
Citizens' perceptions and expectations are not decoration on the twin; they
are one of its four constitutive domains.

The difficulty is that the relevant intellectual tradition — the sociology of
place, meaning and collective experience — is abstract, and much of it
predates the information systems that could now operationalize it. The link
between that tradition and knowledge organization is evident at the abstract
level but has rarely been carried into working information models. Providing
that operationalization is a purpose of this RFC.

A second difficulty is a persistent modeling temptation: to construct the
population as a rich set of individual records — synthetic or real — and
derive collective properties by aggregation. Turner's account of
macrostructural dynamics argues that this cannot succeed: macro-level social
patterns are not adequately conceptualized by sampling micro-level units,
however detailed the individual view. The population dimension therefore
requires a collective model in its own right, anchored to spatial reality
through the Spatial Referent.

# Terminology

## Definition

> **Definition RFC0080-D1 — Place**
>
> The Semantic Interpretation through which the population domain understands
> a Spatial Referent: the referent's entity as experienced, used and given
> meaning by people.

---

> **Definition RFC0080-D2 — Membership Criterion**
>
> An intensional definition of a collective with respect to a Place, such as
> residents of an area, daily users of a park or evening users of an
> underpass. A Membership Criterion qualifies Collective State claims; it
> does not define an entity and does not require enumeration of members.

---

> **Definition RFC0080-D3 — Collective State**
>
> A temporally qualified state claim about the social dimension of a Place or
> a Configuration, made with respect to a Membership Criterion, that exists
> at the collective level and is not derivable as an aggregation of
> individual-level records. Examples of Collective State variables include
> attributed meaning, perceived safety and perceived comfort.

---

> **Definition RFC0080-D4 — Perception Signal**
>
> The role an observation (RFC 0040) plays when it serves as evidence for
> estimating Collective State. Perception Signal is a role, not a distinct
> kind of observation.

---

> **Definition RFC0080-D5 — Configuration**
>
> A set of Places together with relationships among them, over which
> Collective State may be defined when the state of interest is a property
> of the configuration rather than of any single Place.

## Scope

This RFC specifies:

- the population domain's interpretation of the Spatial Referent as Place;
- the expression of the population dimension as Collective State;
- the qualification of state claims by Membership Criterion and time;
- Collective State over Configurations of Places;
- the separation between individual-level evidence and collective-level
  claims.

## Not in Scope

This RFC does not specify:

- observation semantics, which belong to RFC 0040; the population domain
  consumes observations and does not redefine them;
- survey instruments, sentiment analysis methods or estimation techniques;
- criteria for the sufficiency, representativeness or weighting of evidence
  (see Note RFC0080-N9);
- synthetic population construction or agent-based simulation;
- personal data management, which belongs to the separate construct of the
  Personal Digital Twin and to applicable data protection law;
- demographic statistics production.

# Core Concepts

## The referent as Place

The population domain adds a viewpoint to the Spatial Referent in exactly the
way other domains do: as the geospatial domain sees a geometry and the asset
domain sees an asset, the population domain sees a Place. Place is not a new
entity; it is the population domain's Semantic Interpretation of the same
referent (RFC0010-D1), joined on the same Persistent Identity, under the
Orthogonal Semantic Domains Principle (RFC0001-P2).

> **Note RFC0080-N1 — Lefebvre's triad and domain orthogonality**
>
> The framework's factoring echoes Lefebvre's distinction between conceived,
> perceived and lived space. Conceived space — the planners' and surveyors'
> representation — corresponds to the geospatial domain's Geometric
> Interpretation. Perceived space — spatial practice, how the entity is
> actually used — surfaces in observation and activity domains. Lived space —
> the meanings people attach — is the population domain's Place. The triad
> is thus realized as domain orthogonality over one referent, rather than as
> competing models of the same thing.

## Population as state, not entity

The population dimension is expressed entirely as Collective State. The
framework models no population entity, because nothing about a collective
needs to persist independently of state claims. Membership churns
continuously, so there is no stable extension to identify. Apparent
continuity — the residents of a neighbourhood over decades — is continuity
of the Place and the Membership Criterion, not of any collective object: the
members are entirely replaced while the criterion and the place remain. The
subject of interest is the place and the patterns and changes of its social
dimension; the population is the live snapshot those states describe.

Plurality survives without a bearer. Distinct Membership Criteria qualify
distinct state claims for the same Place — perceived safety among evening
users, perceived comfort among residents — and divergence between them is
information, not inconsistency.

> **Note RFC0080-N2 — Plural and relational place**
>
> Following Massey, a Place has no single essential identity: its meaning is
> plural, contested and produced partly by relations that extend beyond its
> boundaries. The framework accommodates this by permitting multiple
> Membership Criteria and multiple Collective State claims per Place, by not
> requiring that a Membership Criterion be spatially contained by any
> Geometric Interpretation of the referent, and by allowing Collective State
> over Configurations.

> **Note RFC0080-N3 — Durkheim's social facts**
>
> The justification for treating Collective State as irreducible is
> Durkheim's concept of the social fact: ways of acting, thinking and
> feeling that are external to any individual and exert influence over
> individuals. The perceived safety of a place is such a fact — it shapes
> individual behaviour (routes chosen, hours avoided) and persists while the
> people present change. The social fact persists as a property of the
> milieu, not of any enumerable membership: this is precisely state attached
> to Place, and it is why the population dimension requires no entity.

## Estimation, not aggregation

Individual perceptions enter the population domain only in the Perception
Signal role: observations serving as evidence from which Collective State is
estimated. Citizen reports, proactive survey responses and sensor-mediated
signals are all observations in the sense of RFC 0040; the population domain
consumes them. The knowledge produced is never a sum of signals but the
output of analysis capable of identifying patterns and changes — the
relationship between signals and Collective State is the same as that
between sensor readings and the condition of an asset. Estimation may be
statistical, qualitative or deliberative; the framework does not prescribe
the method. What it prescribes is the separation: signals are evidence,
Collective State is a claim, and the claim is never merely the arithmetic of
the signals.

> **Note RFC0080-N9 — Evidence positioning, not evidence assessment**
>
> The framework takes the architectural position that it is not in a
> position to assess evidence. Representativeness, sufficiency and weight of
> Perception Signals are use-case specific judgements that belong to whoever
> makes the Collective State claim, under their own governance. What the
> semantic level guarantees is positioning: every signal has a place in the
> model — anchored to the Spatial Referent it concerns, temporally
> qualified, and linkable as potential evidence to the claims it may support
> — so that any assessment, however use-case specific, finds its context
> ready. This parallels the Governance Authority Principle (RFC0001-P4): as
> the framework does not determine authoritative interpretations, it does
> not determine authoritative evidence.

> **Note RFC0080-N4 — Patterns of change as Turner's processes**
>
> Turner's macrostructural theory names three fundamental processes:
> assemblage, differentiation and integration. In this framework they serve
> as a vocabulary for classes of Collective State change that analysis looks
> for: concentration of concern around a place (assemblage), divergence of
> state between criteria or between places (differentiation), and
> convergence or stabilization across a Configuration (integration).
> Population dynamics are thereby expressed as state transitions, consistent
> with the Universal State Principle (RFC0001-P3).

## Collective State over Configurations

Some collective states are properties of no single Place: the perceived
safety of a route is a property of the chain of places it traverses; the
social meaning of a square is co-produced by the streets feeding it;
segregation is a differential across adjacent areas. For these, Collective
State is defined over a Configuration (RFC0080-D5): a set of Places and the
relationships among them. This is the conceptual reason population modeling
requires different capabilities than observation modeling. Observations
relate a stream of results to one feature of interest; configurational state
requires traversing relationships among referents.

> **Note RFC0080-N5 — The privacy dividend**
>
> Because Collective State is claimed at the collective level and Membership
> Criteria are intensional, the population domain requires no person-level
> identity. Observations in the Perception Signal role may be processed and
> discarded or held in de-identified form under the governance of their
> collecting domain. This structurally separates the Urban Digital Twin's
> population dimension from the Personal Digital Twin, which manages
> individual-level data under individual control, and it answers the
> surveillance concern on architectural rather than procedural grounds.

> **Note RFC0080-N6 — Resolution of the entity question**
>
> Draft 0.1 modeled a Population entity bearing Collective State, with
> plurality of populations per place as the argument for an entity as bearer
> (former Issue RFC0080-I1). Draft 0.2 resolves the question in favour of
> state: the bearer argument dissolves once the Membership Criterion is a
> qualifier of the state claim, no property of a collective persists outside
> its state claims, and the continuity intuition attaches to Place and
> criterion rather than to a collective object. The identifier RFC0080-I1 is
> retired and shall not be reused.

> **Note RFC0080-N7 — Synthetic populations as instruments**
>
> Synthetic populations and agent-based simulations are instruments that
> realize scenarios over the population dimension; they are not the
> population dimension. A synthetic population is calibrated against
> Collective State and statistical distributions, and its simulated outcomes
> may in turn serve as evidence. Treating the synthetic construct as the
> population itself would reintroduce the aggregation fallacy with generated
> rather than observed individuals.

# Semantic Relationships

Within the population domain:

- a **Place** is a Semantic Interpretation of exactly one Spatial Referent,
  joined by Persistent Identity (RFC0010-R3);
- a **Collective State** claim is qualified by a Place or a Configuration, a
  Membership Criterion and time;
- a **Configuration** consists of Places and relationships among them; the
  relationships reference Spatial Referents by Persistent Identity;
- an observation acts in the **Perception Signal** role when cited as
  evidence for a Collective State claim; observation semantics remain with
  RFC 0040.

# Design Principles

## Principle RFC0080-P1 — Collective Irreducibility Principle

> Collective State **shall not** be defined as an aggregation of
> individual-level records.

## Principle RFC0080-P2 — Place Interpretation Principle

> Place **shall** be expressed as the population domain's Semantic
> Interpretation of a Spatial Referent, not as a separate entity with its own
> identity.

## Principle RFC0080-P3 — Population-as-State Principle

> The population dimension **shall** be expressed as Collective State of
> Places and Configurations. No population entity with a Persistent Identity
> is defined by this framework.

# Normative Requirements

> **Requirement RFC0080-R1 — Criterion qualification**
>
> Every Collective State claim shall be qualified by a Membership Criterion.
> An enumeration of members shall not be required for a claim to be made or
> maintained.

---

> **Requirement RFC0080-R2 — Collective-level claims**
>
> Collective State shall be claimed for a Place or a Configuration, and shall
> be temporally qualified.

---

> **Requirement RFC0080-R3 — Evidence separation**
>
> Individual-level data shall enter the population domain only as
> observations in the Perception Signal role. A Collective State claim
> should record the nature of its supporting evidence.

---

> **Requirement RFC0080-R4 — No person-level identity**
>
> The population domain shall not require persistent person-level identity.
> Governance of observations in the Perception Signal role, including
> retention and de-identification, belongs to the Governing Authority of the
> collecting domain.

---

> **Requirement RFC0080-R5 — Plurality**
>
> Multiple Collective State claims may coexist for the same Place or
> Configuration under distinct Membership Criteria. Divergent claims under
> distinct criteria shall not be treated as contradictions requiring
> resolution.

---

> **Requirement RFC0080-R6 — Configurational reference**
>
> A Configuration shall reference its Places, and express relationships among
> them, through Spatial Referent identities rather than through descriptive
> content.

---

> **Requirement RFC0080-R7 — Signal positioning**
>
> An observation acting in the Perception Signal role shall be positioned in
> the model by reference to the Spatial Referent identity of the Place or
> Configuration it concerns and by temporal qualification. Positioning
> establishes a signal as potential evidence; it shall not imply any
> judgement of its representativeness or weight.

# Examples

> **Example RFC0080-E1 — Perceived safety of an underpass**
>
> A pedestrian underpass is a Spatial Referent with an Anchor Geometry.
> Citizen reports mentioning fear near the location, a proactive perception
> survey and a participatory planning response provide observations in the
> Perception Signal role. From these, analysis produces a Collective State
> claim: perceived safety, under the criterion of evening users, is low and
> has deteriorated over two years. The city improves lighting — an
> intervention recorded in the asset domain against the same referent — and
> subsequent signals support a revised state claim. The evidence loop closes
> over one Persistent Identity, and at no point does any system hold a
> roster of the underpass's users.

---

> **Example RFC0080-E2 — One park, two criteria**
>
> A park carries two families of Collective State claims: under the
> criterion of nearby residents, attributed meaning is everyday and
> perceived comfort is declining; under the criterion of weekend visitors,
> the park is a destination and satisfaction is high. Both claims are held,
> each qualified by its criterion. The divergence directs attention to what
> differs — time of use, expectations, exposure to the maintenance backlog
> recorded in the asset domain — rather than being averaged away.

---

> **Example RFC0080-E3 — A route as Configuration**
>
> A walking route from a transit stop to a school traverses a sequence of
> street segments and crossings, each a Spatial Referent. The perceived
> safety of the route, under the criterion of schoolchildren's caregivers,
> is a Collective State of the Configuration: it depends on the weakest
> segments and on the relationships between them, and it is not the state of
> any single Place nor an average over them. An intervention at one crossing
> can change the state of the whole Configuration.

# Planned Figures

> **Figure RFC0080-F1 (placeholder)**
>
> The population domain's viewpoint: Spatial Referent as Place, Collective
> State qualified by Membership Criterion and time, observations in the
> Perception Signal role as evidence.
>
> *[Diagram to be inserted: fig-rfc0080-f1-population-viewpoint.svg]*

---

> **Figure RFC0080-F2 (placeholder)**
>
> Estimation versus aggregation: individual signals as evidence for a
> collective claim, contrasted with the aggregation fallacy.
>
> *[Diagram to be inserted: fig-rfc0080-f2-estimation-vs-aggregation.svg]*

---

> **Figure RFC0080-F3 (placeholder)**
>
> Collective State over a Configuration: a route as a related set of Places
> whose state is a property of the configuration.
>
> *[Diagram to be inserted: fig-rfc0080-f3-configuration-state.svg]*

# Standards and Implementation Mappings

The following correspondences are informative.

| Framework concept | Correspondence (informative) |
|---|---|
| Place / population state / resource context | Turner's SPACE, POPULATION and RESOURCES; POPULATION is realized as the state dimension, not as a modeled object |
| Collective State | Durkheim's social fact; state variables in quantitative sociology |
| Perception Signal role | Open311 service requests and free-text descriptions; proactive perception surveys; participatory GIS and SoftGIS data points |
| Signal anchoring | OGC SensorThings `FeatureOfInterest` carrying the Spatial Referent's identity |
| Configuration | Property graphs and graph databases; nodes as referent identities, edges as typed relationships |
| Structural context | Population statistics at administrative-unit level (INSPIRE Annex III themes) |
| Simulation instrument | Synthetic populations and agent-based models, calibrated against Collective State |

> **Note RFC0080-N8 — Divergent implementation capabilities**
>
> The observation side of the population domain fits the established pattern
> of result streams against a feature of interest, well served by
> time-series and document storage. Configurational state instead requires
> traversal of relationships among referents, for which graph-like
> capabilities are the natural implementation binding. The framework
> deliberately keeps both under one semantic model while expecting their
> implementations to differ.

# Open Questions

> **Issue RFC0080-I2 — Boundary with Observation** *(resolved in Draft 0.2)*
>
> Resolved: observation semantics belong to RFC 0040. The population domain
> defines only the Perception Signal role (RFC0080-D4). RFC 0040 should be
> drafted to confirm that Open311-style civic reports are representable as
> observations.

---

> **Issue RFC0080-I3 — Extent of configurational semantics**
>
> Collective State over Configurations (RFC0080-D5) addresses relational
> place at the level of state claims. Open: does the framework need to
> define relationship types within Configurations (adjacency, traversal,
> feeding), or are these domain-owned interpretations?

---

> **Issue RFC0080-I4 — Meaning and interpretation**
>
> Attributed meaning is the least operationalized Collective State variable.
> Its formal treatment may belong with the semiotic grounding planned for
> RFC 0015.

---

> **Issue RFC0080-I5 — Legitimacy of evidence** *(resolved in Draft 0.3)*
>
> Resolved: the legitimacy and representativeness of evidence are
> operational, use-case specific questions outside the semantic level. The
> framework guarantees the positioning of every signal as potential evidence
> (RFC0080-R7, Note RFC0080-N9) and deliberately does not assess evidence.
> Assessment belongs to the governance under which a Collective State claim
> is made; RFC 0060 may address who may make claims, but not evidence
> methodology.

# References

- RFC 0000 — Introduction
- RFC 0001 — Design Principles
- RFC 0002 — Terminology and Naming Conventions
- RFC 0010 — Spatial Referent
- RFC 0040 — Observation (planned)
- RFC 0060 — Governance and Authority (planned)
- Editorial Style Guide
- J. H. Turner, "A General Theory of Macrostructural Dynamics," in
  *Sociological Theories in Progress*, 1989. (informative)
- É. Durkheim, *The Rules of Sociological Method*, 1895. (informative)
- H. Lefebvre, *The Production of Space*, 1974. (informative)
- D. Massey, "A Global Sense of Place," 1991; *For Space*, 2005. (informative)
- M. Batty, Editorial, *Environment and Planning B*, vol. 28, 2001.
  (informative)
