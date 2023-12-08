# Schemas Overview

## General Schema
  - <b id="#/properties/name">name</b>
	 - _please use printable ascii characters without blank_
	 - Type: `string`
	 - <i id="/properties/name">path: #/properties/name</i>
	 - The value must match this pattern: `^([!-~])+$`
	 - Length:  &le; 256

 - <b id="#/properties/description">description</b>
	 - Type: `string`
	 - <i id="/properties/description">path: #/properties/description</i>
	 - The value must match this pattern: `(.|)*`
	 - Length:  &le; 8192



 - <b id="#/properties/versioning">versioning</b>
	 - Type: `object`
	 - <i id="/properties/versioning">path: #/properties/versioning</i>
	 - **_Properties_**
		 - <b id="#/properties/versioning/properties/version">version</b>
			 - Type: `string`
			 - <i id="/properties/versioning/properties/version">path: #/properties/versioning/properties/version</i>
		 - <b id="#/properties/versioning/properties/previousVersion">previousVersion</b>
			 - <i id="/properties/versioning/properties/previousVersion">path: #/properties/versioning/properties/previousVersion</i>
		 - <b id="#/properties/versioning/properties/nextVersion">nextVersion</b>
			 - <i id="/properties/versioning/properties/nextVersion">path: #/properties/versioning/properties/nextVersion</i>


 - <b id="#/properties/provenance">provenance</b>
	 - Type: `object`
	 - <i id="/properties/provenance">path: #/properties/provenance</i>
	 - **_Properties_**
		 - <b id="#/properties/provenance/properties/contributors">contributors</b>
			 - Type: `array`
			 - <i id="/properties/provenance/properties/contributors">path: #/properties/provenance/properties/contributors</i>
				 - **_Items_**
				 - Type: `object`
				 - <i id="/properties/provenance/properties/contributors/items">path: #/properties/provenance/properties/contributors/items</i>
				 - **_Properties_**
					 - <b id="#/properties/provenance/properties/contributors/items/properties/Name">Name</b>
						 - _Full name of the contributor_
						 - Type: `string`
						 - <i id="/properties/provenance/properties/contributors/items/properties/Name">path: #/properties/provenance/properties/contributors/items/properties/Name</i>
					 - <b id="#/properties/provenance/properties/contributors/items/properties/ORCID">ORCID</b>
						 - Type: `string`
						 - <i id="/properties/provenance/properties/contributors/items/properties/ORCID">path: #/properties/provenance/properties/contributors/items/properties/ORCID</i>
		 - <b id="#/properties/provenance/properties/creationDate">creationDate</b>
			 - Type: `string`
			 - <i id="/properties/provenance/properties/creationDate">path: #/properties/provenance/properties/creationDate</i>
			 - String format must be a "datetime"
		 - <b id="#/properties/provenance/properties/lastModificationDate">lastModificationDate</b>
			 - Type: `string`
			 - <i id="/properties/provenance/properties/lastModificationDate">path: #/properties/provenance/properties/lastModificationDate</i>
			 - String format must be a "datetime"

 - <b id="#/properties/ExpectedUse">ExpectedUse</b>
	 - Type: `string`
	 - <i id="/properties/ExpectedUse">path: #/properties/ExpectedUse</i>
	 - String format must be a "textarea"
	 - Length:  &le; 1024

- <b id="#/properties/Aliases">Aliases</b>
	 - _Provide a list of aliases as alternatives to the chosen name._
	 - Type: `array`
	 - <i id="/properties/Aliases">path: #/properties/Aliases</i>
		 - **_Items_**
		 - Type: `string`
		 - <i id="/properties/Aliases/items">path: #/properties/Aliases/items</i>