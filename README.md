## Histograph Schemas

## Ontology

Three namespaces:

| Namespace | Name              | URI
|-----------|-------------------|---------------------------------------
| `hg`      | Histograph        | http://schema.histograph.io/#
| `time`    | Time Ontology     | http://www.w3.org/2006/time#
| `geo`     | GeoSPARQL         | http://www.opengis.net/ont/geosparql#

### Relations

#### Concept

- `hg:conceptIdentical`
- `hg:conceptIsWithin`
- `hg:conceptContains`
- `hg:conceptIntersects`

#### Type

- `hg:typeBroader`
- `hg:typeNarrower`
- `hg:typeIntersects`

#### Geo

http://en.wikipedia.org/wiki/GeoSPARQL

- `geo:sf-disjoint`
- `geo:sf-touches`
- `geo:sf-overlaps`
- `geo:sf-equals`
- `geo:sf-within`
- `geo:sf-contains`
- `geo:sf-intersects`

#### Time

http://www.w3.org/TR/owl-time/#summary

- `time:intervalEquals`
- `time:intervalBefore`
- `time:intervalMeets`
- `time:intervalOverlaps`
- `time:intervalStarts`
- `time:intervalDuring`
- `time:intervalFinishes`
- `time:intervalAfter`
- `time:intervalMetBy`
- `time:intervalOverlappedBy`
- `time:intervalStartedBy`
- `time:intervalContains`
- `time:intervalFinishedBy`

## Elasticsearch mapping

See [`elasticsearch/pit.json`](elasticsearch/pit.json).

## Histograph IO - JSON schemas

[Histograph IO](https://github.com/histograph/io) uses the following [JSON Schema](http://json-schema.org/) files to validate all data going into Histograph:

- PITs: [`json/pits.schema.json`](json/pits.schema.json)
- Relations: [`json/relations.schema.json`](json/relations.schema.json)
- Source metadata: [`json/source.schema.json`](json/source.schema.json)

### schemas-from-ontology.js

`schemas-from-ontology.js` reads the Histograph ontology from [`histograph.ttl`](ontology/histograph.ttl) and writes constraints in JSON schema files ([`json/pits.schema.json`](json/pits.schema.json) and [`json/relations.schema.json`](json/relations.schema.json)).

Install dependencies:

    npm install

Run:

    node schemas-from-ontology.js
