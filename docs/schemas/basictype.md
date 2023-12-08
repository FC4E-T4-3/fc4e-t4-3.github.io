# BasicInfoType

## Schema

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
       - **_AnyOf_**:
           - <b id="#/properties/Test/properties/Type">Type</b> `required`
			 - _For type "Number", further differentiate between integer and float._
			 - Type: `string`
			 - <i id="/properties/Test/properties/Type">path: #/properties/Test/properties/Type</i>
			 - The value is restricted to the following: 
				 1. _"String"_
		 - <b id="#/properties/Test/properties/PropRelations">PropRelations</b>
			 - _Properties are chained by boolean operators. By default, through the AND operator all properties must apply. OR or XOR operators for properties are also possible._
			 - Type: `string`
			 - <i id="/properties/Test/properties/PropRelations">path: #/properties/Test/properties/PropRelations</i>
			 - The value is restricted to the following: 
				 1. _"AND"_
				 2. _"OR"_
				 3. _"XOR"_
		 - <b id="#/properties/Test/properties/Properties">Properties</b>
			 - Type: `array`
			 - <i id="/properties/Test/properties/Properties">path: #/properties/Test/properties/Properties</i>
				 - **_Items_**
				 - Type: `object`
				 - <i id="/properties/Test/properties/Properties/items">path: #/properties/Test/properties/Properties/items</i>
				 - **_Properties_**