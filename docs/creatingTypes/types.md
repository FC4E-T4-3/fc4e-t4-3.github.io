# The Different Data Types

This page explains the purpose of the different data types that can be created in the typeregistry.

## Schema Elements

One main application of the Data Type Registry is the creation of metadata elements of schemas. Registering metadata elements has many 
advantages. These include the unambigious identification via a PID, additional metadata information, and the possibility of reusability and
interoperability of types.

### Basic Info Types
 `BasicInfoTypes` can be considered the basic building blocks, or leaf nodes,  for schema elements. Each `BasicInfoType` is simply
some fundamental data type, with additional metadata and the possibility to apply some restrictions on that type. 

<center>

| BasicInfoType |
|---------------|
| String        | 
| Number        | 
| Boolean       | 
| Enum          | 

</center>

### Info Types

An `InfoType` on the other 
hand is a more complex construct. It shares the set of metadata with `BasicInfoTypes`, but instead of a fundamental data type it represents a 
composite of other types. It can either take the form of an `Object`, which is basically a is a collection of `BasicInfoTypes` and `InfoTypes` that are used to create a new `InfoType`, or an `Array`, where one type can be repeated. The `Tuple` property will be implemented soon.

<center>

| InfoType |
|----------|
| Object   |
| Array    |
| Tuple    |

</center>

### Profiles

Syntactically, a `Profile` is similar to an `InfoType`, but it differs semantically. A `Profile` can only be an object and represents a full schema or kernel information profile (KIP).   

## Taxonomy Nodes

`Taxonomy Nodes` can be used to group types together in a way that is more semantically meaningful. Each `Taxonomy Node` represents just a term with potential parent nodes. This way, `Taxonomy Nodes` can be hierarchically organized. Each other kind of data type can be assigned one or more taxonomy nodes, which can used as custom facets either in the query builder or in the Type API, where the hierarchical nature of the taxonomy nodes can be used to filter results.

## Measurement Units

The DTR offers rudimentary support for measurement units. They can be registered with minimal information assigned to `BasicInfoTypes`. The DTR is not supposed to be a ground truth registry for measurement units, but they serve to enrich other types with more semantic information.

## Extended MIME Types

In a proof of concept, the DTR includes the ability to register extended MIME types. The entire collection of [Media Types from IANA](https://www.iana.org/assignments/media-types/media-types.xhtml) is included in the DTR in machine actionable format and with additional metadata enriched.