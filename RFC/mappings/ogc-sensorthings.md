# OGC SensorThings API

Status: Draft. Non-normative.

This mapping relates the entity model of the OGC SensorThings API (Part 1:
Sensing, OGC 15-078r6) to the concepts of the Urban Digital Twin Semantic
Framework, principally RFC 0040 (Observation) and RFC 0010 (Spatial
Referent).

## Entity mapping

| SensorThings entity | Framework concept | Notes |
|---|---|---|
| `Thing` | Observer (platform aspect) | The hosting arrangement; not the Subject of observations (RFC0040-R2) |
| `Sensor` | Observer (instrument aspect) | Provenance of the observing method |
| `Location` | Observer location | Observer-located pattern |
| `HistoricalLocation` | Observer location over time | Trace-located pattern |
| `Datastream` | Observation Series (RFC0040-D6) | Holds Observer, Observed Property and subject pattern constant |
| `Datastream.observedArea` | Series Scope (RFC0040-D10) | The standard defines it as the bounding envelope of the Datastream's FeaturesOfInterest — the derived mode of RFC0040-D10; a declared scope (e.g. a camera's field of view) extends this usage |
| `ObservedProperty` | Observed Property (RFC0040-D3) | Defined by reference to external vocabularies per RFC0040-R5 |
| `Observation` | Observation (RFC0040-D1) | Immutable per RFC0040-P3 |
| `Observation.result` | Result (RFC0040-D4) | |
| `FeatureOfInterest` | Subject (RFC0040-D5) | Carries the Spatial Referent's identity; subject-located pattern when distinct from `Location` |
| `Observation.resultQuality` | Quality Statement (RFC0040-D7) | Defined by SensorThings as an ISO 19157 data quality element; narrowest (Result) scope of RFC0040-R7 |

## The four location references

SensorThings references location in four ways at different levels of its
entity model, corresponding to the spatial concepts of RFC 0040: the
`Location` of a Thing (observer-located), its `HistoricalLocations`
(trace-located), the `observedArea` of a Datastream (Series Scope) and the
`FeatureOfInterest` of an Observation (subject-located). The parking
surveillance case shows all levels at once: the Thing's Location is the
camera mount, the Datastream's observedArea is the field of view, and each
Observation's FeatureOfInterest is an individual parking spot polygon with
a boolean occupancy result. The framework's normative element is the
binding of the Subject to a Spatial Referent; the Thing's own location is
provenance and the Series Scope serves discovery.

## Notable divergences

- SensorThings models instrument observation; the framework extends the
  same structure to human and computational Observers (RFC0040-P1).
  Human-originated observations (for example Open311 reports, see Note
  RFC0040-N3) have no native SensorThings entity but are representable in
  its pattern.
- SensorThings permits a `FeatureOfInterest` to be generated from the
  Thing's `Location` when none is supplied. Under RFC0040-R3 such a
  generated binding is a resolved binding and its mode must remain
  distinguishable from an asserted one.
- The framework does not adopt SensorThings' Tasking or MQTT parts; they
  concern actuation and transport, which are out of scope for the semantic
  level.
