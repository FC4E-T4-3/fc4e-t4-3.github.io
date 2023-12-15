# BasicInfoType
The BasicInfoType is used to represent any datatype that is some form of a fundamental type, namely strings, numbers, booleans. When restrictions are properly filled, a validation schema can be generated for each BasicInfoType. 
## Schema
- _All fields from the General Schema are included_ 
- <b id="#/properties/MeasuredUnits">MeasuredUnits</b>
	 - _Units that are measured using this type._
	 - Type: `array`
	 - <i id="/properties/MeasuredUnits">path: #/properties/MeasuredUnits</i>
		 - **_Items_**
		 - <i id="/properties/MeasuredUnits/items">path: #/properties/MeasuredUnits/items</i>
 - <b id="#/properties/Taxonomies">Taxonomies</b>
	 - _Taxonomy nodes that this type should be assigned to._
	 - Type: `array`
	 - <i id="/properties/Taxonomies">path: #/properties/Taxonomies</i>
		 - **_Items_**
		 - <i id="/properties/Taxonomies/items">path: #/properties/Taxonomies/items</i>

 - <b id="#/properties/Schema">Schema</b>
	 - _Select the fundamental datatype this type should represent. "Number" can be further differentiated into integer and float._
	 - Type: `object`
	 - <i id="/properties/Schema">path: #/properties/Schema</i>
	 - **_Properties_**
       - The properties of the schema branch here into different directions based on the desired fundamental datatype. For each fundamental type, different restrictions are valid and internal validation is conducted accordingly. We now list the possibilities for each datatype.
           - <b id="#/properties/Test/properties/Type">Type</b> `required`
			 - _For type "Number", further differentiate between integer and float._
			 - Type: `string`
			 - <i id="/properties/Test/properties/Type">path: #/properties/Test/properties/Type</i>
			 - The value is restricted to the following: 
				 1. _"String"_
				 1. _"Integer"_
				 1. _"Number"_
				 1. _"Boolean"_
				 1. _"Enum"_
				 1. _"None"_
		 - <b id="#/properties/Test/properties/PropRelations">PropRelations</b>
			 - _Properties are chained by boolean operators. By default, through the AND operator all properties must apply. OR or XOR operators for properties are also possible._
			 - Type: `string`
			 - <i id="/properties/Test/properties/PropRelations">path: #/properties/Test/properties/PropRelations</i>
			 - The value is restricted to the following: 
				 1. _"AND"_
				 2. _"OR"_
				 3. _"XOR"_
		 - <b id="#/properties/Test/properties/Properties">Properties</b>
			 - Type: `array/string`
			 - <i id="/properties/Test/properties/Properties">path: #/properties/Test/properties/Properties</i>
			 -  _The allowed values in the properties field depend on the desired fundamental type. Strings, Integers and Numbers have an array like described in the `items` field below. Note that when using field names described by the json-schema definition (i.e. minLength, maxLength...) the values are validated internally to avoid issues on the schema creation._
				 - **_Items_**
				 - Type: `object`
				 - <i id="/properties/Test/properties/Properties/items">path: #/properties/Test/properties/Properties/items</i>
				 - **_Properties_**
        		    -  <b id="#/properties/Property">Property</b>
                    	 - Type: `string`
                    	 - <i id="/properties/Property">path: #/properties/Property</i>
                   -   <b id="#/properties/Value">Value</b>
                     	 - Type: `string`
                     	 - <i id="/properties/Value">path: #/properties/Value</i>
         	 - _If the selected Type is  `boolean`, the `Properties` field is only one optional string, which may take one of the following two values._
         	 - Type: `string`

    			1. _"Always True"_
    			2. _"Always False"_


				- Type: `string`
				- <i id="/properties/Property">path: #/properties/Property</i>
				- The value is restricted to the following: 
					1. _"Integer Enum"_
			- <b id="#/properties/Value">Value</b>
				- Type: `array`
				- <i id="/properties/Value">path: #/properties/Value</i>
					- **_Items_**
					- #### Enum Element
					- Type: `integer`
					- <i id="/properties/Value/items">path: #/properties/Value/items</i>