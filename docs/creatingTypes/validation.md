# Schema Generation and Validating Data

One of the main applications of the Data Type Registry is the creation of metadata elements of schemas, constructing complex objects that serve as metadata profiles, and validating data against those profiles. The TypeAPI offers endpoints for all those functionalities, which we will discuss on this page.

## Schema Generation

The generation of JSON schemas is possible for all types describing metadata elements, so `BasicInfoTypes`, `InfoTypes` and `Profiles`.

The basic endpoint to generate a JSON schema is 

```
https://typeapi.lab.pidconsortium.net/v1/types/schema/{prefix}/{suffix}
```

where `prefix` and `suffix` describe the data type in question. Note that the @id property is used to identify all types used in complex schemas.

## Validating Data

Once a schema is generated it can be used to validate data against it. There are many possibilities for this, but the TypeAPI offers an endpoint to directly validate data against a type, without the need to manually generate the schema. To validate data, send a `POST` request to

```
https://typeapi.lab.pidconsortium.net/v1/types/validate/{prefix}/{suffix}
```
where `prefix` and `suffix` describe the data type against which to validate. The body of the `POST` request contains the data to be validated. Take this `cURL` command as an example:

```
curl -X 'POST' \
  'https://typeapi.lab.pidconsortium.net/v1/types/validate/21.T11969/3df63b7acb0522da685d' \
  -H 'accept: text/plain' \
  -H 'Content-Type: application/json' \
  -d '"This is a string"'
```

This validates against the simple "String" `BasicInfoType` and either confirms the validity of the data, or returns a list of errors on how the data does not fit the schema.