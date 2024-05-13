# Creating Schema Elements from Scratch

One main application of the Data Type Registry is the creation of metadata elements of schemas. Registering metadata elements has many 
advantages. These include the unambigious identification via a PID, additional metadata information, and the possibility of reusability and
interoperability of types. In this tutorial, we will walk through the entire creation of schema elements, starting with the fundamental 
building blocks and ending at the generation of JSON schemas of complex data types.

## What are Schema Elements in the DTR?

When clicking `Create`, the possible types that are available can seem overwhelming at first. That is why we want to shed some light on 
the kinds of data types relevant for the creation of schema elements. In general, we differentiate between two different structures with
different responsibilities. `BasicInfoTypes` can be considered the basic building blocks, or leaf nodes,  for schema elements. Each `BasicInfoType` is simply
some fundamental data type, with additional metadata and the possibility to apply some restrictions on that type. An `InfoType` on the other 
hand is a more complex construct. It shares the set of metadata with `BasicInfoTypes`, but instead of a fundamental data type it represents a 
composite of other types. It can either take the form of an `Object`, which is basically a set of key - value pairs where the values are other types,
or an `Array`, where one type can be repeated. The `Tuple` property will be implemented soon. The following table gives a quick overview over which type 
can represent what:

|BasicInfoType   |InfoType   |
|:-:|:-:|
| String  |Object   |
| Number  |Array   |
| Boolean  |Tuple   |

We will start now by creating a `BasicInfoType` to descibe a single property of an existing metadata schema. 

## Creating a BasicInfoType

For the creation of our `BasicInfoType` we will use an actual metadata schema as a blueprint. This hopefully helps in following along the parallels and how 
the schema is created hierarchically in the DTR. Take a look at [the following schema](https://git.gesis.org/konsortswd/pid-registration-service/-/blob/main/src/main/resources/nfdi/nfdi.json?ref_type=heads) from KonsortSWD, which develop infrastructure for research data for the
social sciences in the scope of the NFDI.

When untangling the `$ref` properties we see that the schema is basically an object containing just an array called `variables`, where each variable has a number of properties. To now recreate this schema in the DTR we have to start from the bottom and gradually build the schema up hierarchically. So let us zoom in on one of those
basic properties, the first one in the list:
```
 "studyDOI": {"type": "string","pattern": "[1][0][/.].*"},
```
We see that it represents the fundamental data type `string` and applies a restriction in the form of a regular expression, just called `pattern` in JSON-Schema. Now we want to create this property as `BasicInfoType` in the DTR. Of course this is all possible via the API, but we consider the process via the UI for now. Take a look at tje []
### Generating a JSON Schema

Lorem Ipsum

## Creating an Info Type
### Effects of the different fields on the Schema