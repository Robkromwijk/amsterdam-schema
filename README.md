<div align="center">
  <img width="100px" src="amsterdam-schema.svg" />
</div>

# Amsterdam Schema

This repository contains a work-in-progress version of the Amsterdam Schema. Currently, Amsterdam Schema is a set of [JSON Schemas](https://json-schema.org/) and meta-schemas. The goal of this project is to describe and validate [open data published by the City of Amsterdam](https://api.data.amsterdam.nl/api/). Amsterdam Schema will be used to make the import, storage and publishing layers of our APIs more generic, easier to maintain, and better documented.

For more information, see:

- [Werkbestand Team Dataservices](https://observablehq.com/@bertspaan/werkbestand-team-dataservices)
- [Amsterdam Schema Playground](https://observablehq.com/@bertspaan/amsterdam-schema-playground)
- [Amsterdam Schema Importwizard](https://amsterdam-schema-importwizard.glitch.me/)
- [Amsterdam Schema Validator](https://observablehq.com/@bertspaan/amsterdam-schema-validator)

__All schemas currently use the https://ams-schema.glitch.me/ base URI. This URI will change to something like https://schemas.data.amsterdam.nl/ very soon. Currently, a simple proxy running on Glitch is forwarding requests to GitHub. For details, see https://glitch.com/~ams-schema.__

## Schemas

JSON Schema can be used to validate and model JSON data, of any form.

Amsterdam Schema aims to restrict the structure and format of data accepted by Amsterdam's open data systems, in order to make the storing and publishing or different datasets more structured, simpler and better documented.

Amsterdam Schema consists of a standard library of available data types, in the form of JSON Schema meta-schemas. These meta-schemas that are uses to validate JSON Schemas that describe different datasets.

For example:

- The dataset `bag` contains data for each building and address in the city;
- A JSON Schema describes this dataset, a schema exists for each _type_ in the dataset (e.g. buildings and addresses);
- Amsterdam Schema is used to validate these dataset schemas: Amsterdam Schema requires each object of each type to have an `id` field, defines a way to specify relationships, expects all `geometry` fields to be a GeoJSON geometry, et cetera.

## Validation

You can use any JSON Schema validator to validate data against a JSON Schema.

To validate data from your browser, you can use the [Amsterdam Schema Validator 👩🏼‍🏫](https://observablehq.com/@bertspaan/amsterdam-schema-validator). With the `data=data:text/x-url,` and `schema=data:text/x-url,` URL parameters, you can load data and schema JSON files from URLs. For example, to verify the schema https://ams-schema.glitch.me/dataset/bag/pand with meta-schema https://ams-schema.glitch.me/core/meta/object@v0.0.1, open the following link:

https://observablehq.com/@bertspaan/amsterdam-schema-validator?data=data:text/x-url,https%3A%2F%2Fams-schema.glitch.me%2Fdataset%2Fbag%2Fpand&schema=data:text/x-url,https%3A%2F%2Fams-schema.glitch.me%2Fcore%2Fmeta%2Fobject%40v0.0.1

## Versioning

We're currently using [GitHub releases](https://github.com/Amsterdam/amsterdam-schema/releases) to publish different versions of Amsterdam Schema.

The [Glitch app](https://glitch.com/~ams-schema) mentioned above acts as a proxy, and reads the JSON Schemas from this repository from all available releases:

- https://ams-schema.glitch.me/core/schema ⟶ https://raw.githubusercontent.com/Amsterdam/amsterdam-schema/master/schema.json
- https://ams-schema.glitch.me/core/schema@v0.0.1 ⟶ https://raw.githubusercontent.com/Amsterdam/amsterdam-schema/v0.0.1/schema.json
- https://ams-schema.glitch.me/core/meta/object ⟶ https://raw.githubusercontent.com/Amsterdam/amsterdam-schema/master/meta/object.json

## Examples

For examples of dataset schemas conforming to Amsterdam Schema, see https://github.com/Amsterdam/amsterdam-schema-tools/tree/master/schemas.