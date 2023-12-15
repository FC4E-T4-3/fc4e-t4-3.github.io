# TaxonomyNode
`TaxonomyNodes` describe a hierarchical structure of vocabularies. Any other prepared schema type can assigned one or more `TaxonomyNodes`. Via the `TypeAPI`, Taxonomies can resolved and all types returned that are somewhere in the subtree of the selected `TaxonomyNode`.
## Schema
 - _All fields from the General Schema are included_ 
- <b id="#/properties/reference">reference</b>
	 - _External reference to the taxonomy node._
	 - Type: `string`
	 - <i id="/properties/reference">path: #/properties/reference</i>
 - <b id="#/properties/parents">parents</b>
	 - Type: `array`
	 - <i id="/properties/parents">path: #/properties/parents</i>
		 - **_Items_**
		 - <i id="/properties/parents/items">path: #/properties/parents/items</i>