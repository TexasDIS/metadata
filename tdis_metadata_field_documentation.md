# TDIS Metadata Documentation
*Last revised: 2022-10-24*

## Metadata Organization
Within the current TDIS model, "collections" contain "artifacts", "data layers", and "models." 
Data layers can also contain "features", and models can have an associated "configuration". 
Collections, artifacts, data layers, features, models, and configurations each have descriptive metadata associated with them.  

![TDIS Model Diagram](https://github.com/TexasDIS/metadata/blob/main/visuals/tdis-model-diagram.png)

Collections group one or more layers, artifacts and/or models together. 
For example, a complex geospatial database object would be represented as a collection containing multiple data layers.

Artifacts represent digital objects such as text and images within documents, data within spreadsheets, or other data made available via service endpoints. 
Artifacts do not contain geometry information (points, lines, or polygons) or images with spatial information. 

Data layers represent digital objects with intrinsic spatial characteristics and include (but are not limited to) streets, city boundaries, river gages, and imagery with geospatial information contained within files or made available via service endpoints. 

Features, as a part of a data layer, are a record-by-record description of each independent “row” in a geospatial attribute table or database. 

Models represent model software packages and configurations, which may be associated with input and/or output artifacts or data layers. 
Model configurations represent a unique way of running a model, exposing concrete inputs, outputs, and parameters. These metadata are under active development.

### Field Definition Glossary 
Each metadata field below is defined with the following elements:

- **Field Name**: A display name for the metadata field.
- **Description**: Text describing the information that the metadata field should contain as a value. 
- **Use**: An indication of whether the metadata field is "Required", "Recommended", "Optional", "Conditionally Required", or "Conditionally Recommended" within the level (e.g. Collection, Artifact, Data Layer, Feature).
- **Use Condition**: The condition dictating when a "Conditionally Required" metadata field becomes "Required", or a "Conditionally Recommended" metadata field becomes "Recommended". "None" indicates that there are no conditions.
- **Accepts Multiple Values**: "Yes" indicating that multiple values can be added to the metadata field, or "No".
- **Format**: Indication of the type of value the field takes, this will be used for validation.
- **Controlled Terms URL**: A link to published terms that are valid.

## Artifact
### Access
**Field Name**: Distribution Method  
**Description**: A statement describing the method of distribution and access provided by the Distributor or Publisher.  
**Use**: Conditionally Required  
**Use Condition**: Distributor or Publisher  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Distribution URL  
**Description**: The URL where the digital object can be accessed via a service endpoint, API, etc.  
**Use**: Conditionally Required  
**Use Condition**: Distributor or Publisher  
**Accepts Multiple Values**: No  
**Format**: URL  
**Controlled Terms URL**: None  

**Field Name**: Distributor or Publisher  
**Description**: The organization sharing, publishing, or otherwise responsible for providing access to the digital object.  
**Use**: Conditionally Required  
**Use Condition**: Distribution URL  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/organization_terms.csv  

**Field Name**: Service Endpoint Type  
**Description**: The type of service endpoint used for distribution.  
**Use**: Conditionally Required  
**Use Condition**: Service Endpoint URL  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/service_endpoint_types.csv  

### Administrative
**Field Name**: Collection Identifier  
**Description**: The TDIS unique identifier for the associated collection.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: TDIS Identifier: UUID  
**Controlled Terms URL**: None  

**Field Name**: Creation Date  
**Description**: Date the digital object was originally created. Must conform to the ISO 8601 standard.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Date Last Updated  
**Description**: The date the digital object was last updated. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Date Metadata Updated  
**Description**: Date the metadata record was last updated. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Date Submitted  
**Description**: Date the digital object or metadata record was submitted to TDIS. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Identifier  
**Description**: The TDIS unique identifier for the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: TDIS Identifier: UUID  
**Controlled Terms URL**: None  

**Field Name**: License  
**Description**: License associated with the digital object.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Update Frequency  
**Description**: How often the content is updated.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/update_frequency_terms.csv  

**Field Name**: Use Constraint  
**Description**: Constraints or restrictions on use of the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/use_constraint_terms.csv  

**Field Name**: Version  
**Description**: Version number of the digital object.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: None  
**Controlled Terms URL**: None  

### Contact Information
**Field Name**: Contact Affiliation  
**Description**: Organizational affiliation for the responsible point of contact.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/organization_terms.csv  

**Field Name**: Contact Department  
**Description**: Dept under the Contact Affiliation  
**Use**: Conditionally Required  
**Use Condition**: Contact Affiliation  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**:   

**Field Name**: Contact Email  
**Description**: Email for the responsible point of contact.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Name  
**Description**: Name of a person who is a responsible point of contact.  
**Use**: Required for Collection, Optional for Artifact, Layer, and Model  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Phone Number  
**Description**: Work phone number for the responsible point of contact.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Role  
**Description**: The role(s) of the point of contact toward the digital object and its management.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/contact_role_terms.csv  

### Coverage
**Field Name**: Placename or Locality  
**Description**: Placename from GeoNames (http://www.geonames.org).  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text or Controlled Terms  
**Controlled Terms URL**: http://www.geonames.org  

**Field Name**: Spatial Extent (Decimal Degrees)  
**Description**: Coordinates for the bounding box describing the spatial extent covered by the digital object, in decimal degrees.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Array: Decimal Degrees or Geometry: Polygon  
**Controlled Terms URL**: None  

**Field Name**: Time Period Covered  
**Description**: Time period to which the data refer as a single date-time or an interval. Must conform to the ISO 8601 standard. This reflects the time period covered by the data, not the dates of coding or making documents machine-readable or the dates the data were collected. Also known as the "span" covered by the data, this may reflect the dates during which an event occured.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

### Discovery
**Field Name**: Boundary Type  
**Description**: The type of geospatial boundary associated with the digital object.   
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/boundary_type_terms.csv  

**Field Name**: Boundary Unit Identifier  
**Description**: The unique identifier for a geospatial boundary unit of a particular type, such as a name or code.  
**Use**: Conditionally Required  
**Use Condition**: Boundary Type  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/boundary_type_terms.csv  

**Field Name**: Classification System  
**Description**: TBD  
**Use**: TBD  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/classification_system_and_terms.csv  

**Field Name**: Classification Term  
**Description**: TBD  
**Use**: TBD  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/classification_system_and_terms.csv  

**Field Name**: Creator  
**Description**: The name of a person or organization who should be cited as contributing to the initial creation of the digital object. Also referred to as an "author" or "contributor".  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Description   
**Description**: An account of the digital object. The description may include an abstract, a table of contents, or a free-text account.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Keyword Term  
**Description**: Subject matter keywords from the vocabulary chosen in Keyword Vocabulary.  
**Use**: Required  
**Use Condition**: Keyword Vocabulary  
**Accepts Multiple Values**: Yes  
**Format**: Array:Text  
**Controlled Terms URL**: None  

**Field Name**: Keyword Vocabulary  
**Description**: Vocabulary for subject matter keywords listed in Keyword Term.  
**Use**: Conditionally Required  
**Use Condition**: Keyword Terms  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/keyword_vocabulary_terms.csv  

**Field Name**: Purpose  
**Description**: A description of the purpose for the creation of this digital object and/or the expected use.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Software Name  
**Description**: The name of the software used to create or work with the digital object.  
**Use**: Required for Model, Optional for Artifact, Layer  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/software_terms.csv  

**Field Name**: Software Version  
**Description**: The version of the software used to create or work with the digital object.  
**Use**: Required for Model, Optional for Artifact, Layer  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Numeric  
**Controlled Terms URL**: None  

**Field Name**: Title  
**Description**: A name given to the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

### Reuse
**Field Name**: Chain of Custody  
**Description**: A statement of any changes in ownership and custody of the digital object since its creation that are significant for its authenticity, integrity, and interpretation. The statement may include a description of any changes successive custodians made to the digital object.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Processing Step Date  
**Description**: The date when a particular processing step was completed. Must conform to the ISO 8601 standard.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Processing Step Description  
**Description**: Description of the processing step performed on a date. A processing step represents a structural change to the data (such as adding fields) and not the addition of data. There can be several processing steps, each of which may have a different date.  
**Use**: Conditionally Required  
**Use Condition**: Processing Step Date  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Processing Step Source  
**Description**: The name of a person or organization who performed the modifications described in the associated Processing Step Description.  
**Use**: Conditionally Required  
**Use Condition**: Processing Step Date  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

## Collection
### Administrative
**Field Name**: Date Metadata Updated  
**Description**: Date the metadata record was last updated. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Identifier  
**Description**: The TDIS unique identifier for the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: TDIS Identifier: UUID  
**Controlled Terms URL**: None  

**Field Name**: License  
**Description**: License associated with the digital object.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

### Contact Information
**Field Name**: Contact Affiliation  
**Description**: Organizational affiliation for the responsible point of contact.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/organization_terms.csv  

**Field Name**: Contact Department  
**Description**: Dept under the Contact Affiliation  
**Use**: Conditionally Required  
**Use Condition**: Contact Affiliation  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**:   

**Field Name**: Contact Email  
**Description**: Email for the responsible point of contact.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Name  
**Description**: Name of a person who is a responsible point of contact.  
**Use**: Required for Collection, Optional for Artifact, Layer, and Model  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Phone Number  
**Description**: Work phone number for the responsible point of contact.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Role  
**Description**: The role(s) of the point of contact toward the digital object and its management.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/contact_role_terms.csv  

### Coverage
**Field Name**: Scale  
**Description**: The scale of the dataset   
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/scale_range.csv  

**Field Name**: Spatial Extent (Decimal Degrees)  
**Description**: Coordinates for the bounding box describing the spatial extent covered by the digital object, in decimal degrees.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Array: Decimal Degrees or Geometry: Polygon  
**Controlled Terms URL**: None  

### Discovery
**Field Name**: Description   
**Description**: An account of the digital object. The description may include an abstract, a table of contents, or a free-text account.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Keyword Term  
**Description**: Subject matter keywords from the vocabulary chosen in Keyword Vocabulary.  
**Use**: Required  
**Use Condition**: Keyword Vocabulary  
**Accepts Multiple Values**: Yes  
**Format**: Array:Text  
**Controlled Terms URL**: None  

**Field Name**: Keyword Vocabulary  
**Description**: Vocabulary for subject matter keywords listed in Keyword Term.  
**Use**: Conditionally Required  
**Use Condition**: Keyword Terms  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/keyword_vocabulary_terms.csv  

**Field Name**: Purpose  
**Description**: A description of the purpose for the creation of this digital object and/or the expected use.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Title  
**Description**: A name given to the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

### Reuse
**Field Name**: Chain of Custody  
**Description**: A statement of any changes in ownership and custody of the digital object since its creation that are significant for its authenticity, integrity, and interpretation. The statement may include a description of any changes successive custodians made to the digital object.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

## Feature
### Administrative
**Field Name**: Date Last Updated  
**Description**: The date the digital object was last updated. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

### Coverage
**Field Name**: Spatial Extent (Decimal Degrees)  
**Description**: Coordinates for the bounding box describing the spatial extent covered by the digital object, in decimal degrees.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Array: Decimal Degrees or Geometry: Polygon  
**Controlled Terms URL**: None  

### Reuse
**Field Name**: Collection Method  
**Description**: The procedure, technique, or mode of inquiry used to attain data. Also referred to as "Data Capture Method".  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/collection_method_terms.csv  

**Field Name**: Collection Method Description  
**Description**: Description of the data collection method.  
**Use**: Conditionally Required  
**Use Condition**: Collection Method  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Horizontal Accuracy (Meters)  
**Description**: Numeric value for the accuracy in meters.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Numeric  
**Controlled Terms URL**: None  

**Field Name**: Horizontal Accuracy Method  
**Description**: Method for determining accuracy of the data.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/collection_method_terms.csv  

**Field Name**: Vertical Accuracy (Meters)  
**Description**: Numeric value for the accuracy in meters.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Numeric  
**Controlled Terms URL**: None  

**Field Name**: Vertical Accuracy Method  
**Description**: Method for determining accuracy of the data.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/collection_method_terms.csv  

**Field Name**: Vertical Datum  
**Description**: A vertical datum is a surface of zero elevation to which heights of various points are referenced.   
**Use**: Conditionally Required  
**Use Condition**: Vertical Cordinate System  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/datums.csv  

## Layer
### Access
**Field Name**: Distribution Method  
**Description**: A statement describing the method of distribution and access provided by the Distributor or Publisher.  
**Use**: Conditionally Required  
**Use Condition**: Distributor or Publisher  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Distribution URL  
**Description**: The URL where the digital object can be accessed via a service endpoint, API, etc.  
**Use**: Conditionally Required  
**Use Condition**: Distributor or Publisher  
**Accepts Multiple Values**: No  
**Format**: URL  
**Controlled Terms URL**: None  

**Field Name**: Distributor or Publisher  
**Description**: The organization sharing, publishing, or otherwise responsible for providing access to the digital object.  
**Use**: Conditionally Required  
**Use Condition**: Distribution URL  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/organization_terms.csv  

**Field Name**: Service Endpoint Type  
**Description**: The type of service endpoint used for distribution.  
**Use**: Conditionally Required  
**Use Condition**: Service Endpoint URL  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/service_endpoint_types.csv  

### Administrative
**Field Name**: Collection Identifier  
**Description**: The TDIS unique identifier for the associated collection.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: TDIS Identifier: UUID  
**Controlled Terms URL**: None  

**Field Name**: Creation Date  
**Description**: Date the digital object was originally created. Must conform to the ISO 8601 standard.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Date Last Updated  
**Description**: The date the digital object was last updated. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Date Metadata Updated  
**Description**: Date the metadata record was last updated. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Date Submitted  
**Description**: Date the digital object or metadata record was submitted to TDIS. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Identifier  
**Description**: The TDIS unique identifier for the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: TDIS Identifier: UUID  
**Controlled Terms URL**: None  

**Field Name**: Update Frequency  
**Description**: How often the content is updated.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/update_frequency_terms.csv  

**Field Name**: Use Constraint  
**Description**: Constraints or restrictions on use of the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/use_constraint_terms.csv  

### Contact Information
**Field Name**: Contact Affiliation  
**Description**: Organizational affiliation for the responsible point of contact.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/organization_terms.csv  

**Field Name**: Contact Department  
**Description**: Dept under the Contact Affiliation  
**Use**: Conditionally Required  
**Use Condition**: Contact Affiliation  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**:   

**Field Name**: Contact Email  
**Description**: Email for the responsible point of contact.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Name  
**Description**: Name of a person who is a responsible point of contact.  
**Use**: Required for Collection, Optional for Artifact, Layer, and Model  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Phone Number  
**Description**: Work phone number for the responsible point of contact.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Role  
**Description**: The role(s) of the point of contact toward the digital object and its management.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/contact_role_terms.csv  

### Coverage
**Field Name**: Placename or Locality  
**Description**: Placename from GeoNames (http://www.geonames.org).  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text or Controlled Terms  
**Controlled Terms URL**: http://www.geonames.org  

**Field Name**: Scale  
**Description**: The scale of the dataset   
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/scale_range.csv  

**Field Name**: Spatial Extent (Decimal Degrees)  
**Description**: Coordinates for the bounding box describing the spatial extent covered by the digital object, in decimal degrees.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Array: Decimal Degrees or Geometry: Polygon  
**Controlled Terms URL**: None  

**Field Name**: Time Period Covered  
**Description**: Time period to which the data refer as a single date-time or an interval. Must conform to the ISO 8601 standard. This reflects the time period covered by the data, not the dates of coding or making documents machine-readable or the dates the data were collected. Also known as the "span" covered by the data, this may reflect the dates during which an event occured.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

### Discovery
**Field Name**: Boundary Type  
**Description**: The type of geospatial boundary associated with the digital object.   
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/boundary_type_terms.csv  

**Field Name**: Boundary Unit Identifier  
**Description**: The unique identifier for a geospatial boundary unit of a particular type, such as a name or code.  
**Use**: Conditionally Required  
**Use Condition**: Boundary Type  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/boundary_type_terms.csv  

**Field Name**: Classification System  
**Description**: TBD  
**Use**: TBD  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/classification_system_and_terms.csv  

**Field Name**: Classification Term  
**Description**: TBD  
**Use**: TBD  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/classification_system_and_terms.csv  

**Field Name**: Creator  
**Description**: The name of a person or organization who should be cited as contributing to the initial creation of the digital object. Also referred to as an "author" or "contributor".  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Description   
**Description**: An account of the digital object. The description may include an abstract, a table of contents, or a free-text account.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: File Format  
**Description**: The type of content in the digital object, and optionally format. Used when a file or files are uploaded to TDIS.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/file_format.csv  

**Field Name**: Keyword Term  
**Description**: Subject matter keywords from the vocabulary chosen in Keyword Vocabulary.  
**Use**: Required  
**Use Condition**: Keyword Vocabulary  
**Accepts Multiple Values**: Yes  
**Format**: Array:Text  
**Controlled Terms URL**: None  

**Field Name**: Keyword Vocabulary  
**Description**: Vocabulary for subject matter keywords listed in Keyword Term.  
**Use**: Conditionally Required  
**Use Condition**: Keyword Terms  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/keyword_vocabulary_terms.csv  

**Field Name**: Purpose  
**Description**: A description of the purpose for the creation of this digital object and/or the expected use.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Software Name  
**Description**: The name of the software used to create or work with the digital object.  
**Use**: Required for Model, Optional for Artifact, Layer  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/software_terms.csv  

**Field Name**: Software Version  
**Description**: The version of the software used to create or work with the digital object.  
**Use**: Required for Model, Optional for Artifact, Layer  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Numeric  
**Controlled Terms URL**: None  

**Field Name**: Title  
**Description**: A name given to the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

### Reuse
**Field Name**: Attribute Accuracy  
**Description**: A statement giving a general assessment of the overall accuracy or completeness of the attribute table associated with the layer.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Attribute Description  
**Description**: Description of the attribute (field, variable) within the attribute table for this layer.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Attribute Domain Type  
**Description**: Domain for values in the attribute (field, variable) within the attribute table.  
**Use**: Optional   
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/attribute_domain_type_terms.csv  

**Field Name**: Attribute Name  
**Description**: Name of the attribute (field, variable) within the attribute table for this layer.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Chain of Custody  
**Description**: A statement of any changes in ownership and custody of the digital object since its creation that are significant for its authenticity, integrity, and interpretation. The statement may include a description of any changes successive custodians made to the digital object.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Code Set Name  
**Description**: The official name of the established code set.  
**Use**: Conditionally Required  
**Use Condition**: Attribute Domain Type: Established Code Set  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Code Set URL  
**Description**: URL for the established code set.  
**Use**: Conditionally Recommended  
**Use Condition**: Attribute Domain Type: Established Code Set  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Domain Value  
**Description**: Valid value for the attribute.  
**Use**: Conditionally Required  
**Use Condition**: Attribute Domain Type: Enumerated List  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Domain Value Description  
**Description**: Description of the valid value for the attribute.  
**Use**: Conditionally Recommended  
**Use Condition**: Attribute Domain Type: Enumerated List  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Horizontal Coordinate System  
**Description**: A projected coordinate system is a planar system that uses two-dimensional coordinates and linear distance measurements as units. A projected coordinate system is based on a geographic coordinate system and a map projection.  
**Use**: Required  
**Use Condition**: Horizontal Coordinate System  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/coordinate_systems.csv  

**Field Name**: Horizontal Datum  
**Description**: A horizontal datum is a specified coordinate system for a collection of positions on the surface of the earth. Horizontal datums define the geometric relationship between a coordinate system grid and the Earth's surface.  
**Use**: Required  
**Use Condition**: TBD  
**Accepts Multiple Values**: TBD  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/datums.csv  

**Field Name**: Processing Step Date  
**Description**: The date when a particular processing step was completed. Must conform to the ISO 8601 standard.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Processing Step Description  
**Description**: Description of the processing step performed on a date. A processing step represents a structural change to the data (such as adding fields) and not the addition of data. There can be several processing steps, each of which may have a different date.  
**Use**: Conditionally Required  
**Use Condition**: Processing Step Date  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Processing Step Source  
**Description**: The name of a person or organization who performed the modifications described in the associated Processing Step Description.  
**Use**: Conditionally Required  
**Use Condition**: Processing Step Date  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Value Range Maximum  
**Description**: The maximum value in a range of valid values.  
**Use**: Conditionally Required  
**Use Condition**: Attribute Domain Type: Range  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Value Range Minimum  
**Description**: The minimumum value in a range of valid values.  
**Use**: Conditionally Required  
**Use Condition**: Attribute Domain Type: Range  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Vertical Coordinate System  
**Description**: A vertical coordinate system defines the origin for height or depth values. They are used as a reference for specifying heights.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/coordinate_systems.csv  

## Model
### Access
**Field Name**: Distribution Method  
**Description**: A statement describing the method of distribution and access provided by the Distributor or Publisher.  
**Use**: Conditionally Required  
**Use Condition**: Distributor or Publisher  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Distribution URL  
**Description**: The URL where the digital object can be accessed via a service endpoint, API, etc.  
**Use**: Conditionally Required  
**Use Condition**: Distributor or Publisher  
**Accepts Multiple Values**: No  
**Format**: URL  
**Controlled Terms URL**: None  

**Field Name**: Distributor or Publisher  
**Description**: The organization sharing, publishing, or otherwise responsible for providing access to the digital object.  
**Use**: Conditionally Required  
**Use Condition**: Distribution URL  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/organization_terms.csv  

**Field Name**: Service Endpoint Type  
**Description**: The type of service endpoint used for distribution.  
**Use**: Conditionally Required  
**Use Condition**: Service Endpoint URL  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/service_endpoint_types.csv  

### Administrative
**Field Name**: Collection Identifier  
**Description**: The TDIS unique identifier for the associated collection.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: TDIS Identifier: UUID  
**Controlled Terms URL**: None  

**Field Name**: Creation Date  
**Description**: Date the digital object was originally created. Must conform to the ISO 8601 standard.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Date Last Updated  
**Description**: The date the digital object was last updated. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Date Metadata Updated  
**Description**: Date the metadata record was last updated. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Date Submitted  
**Description**: Date the digital object or metadata record was submitted to TDIS. Must conform to the ISO 8601 standard.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

**Field Name**: Identifier  
**Description**: The TDIS unique identifier for the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: TDIS Identifier: UUID  
**Controlled Terms URL**: None  

**Field Name**: License  
**Description**: License associated with the digital object.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Update Frequency  
**Description**: How often the content is updated.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/update_frequency_terms.csv  

**Field Name**: Use Constraint  
**Description**: Constraints or restrictions on use of the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/use_constraint_terms.csv  

**Field Name**: Version  
**Description**: Version number of the digital object.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: None  
**Controlled Terms URL**: None  

### Contact Information
**Field Name**: Contact Affiliation  
**Description**: Organizational affiliation for the responsible point of contact.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/organization_terms.csv  

**Field Name**: Contact Department  
**Description**: Dept under the Contact Affiliation  
**Use**: Conditionally Required  
**Use Condition**: Contact Affiliation  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**:   

**Field Name**: Contact Email  
**Description**: Email for the responsible point of contact.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Name  
**Description**: Name of a person who is a responsible point of contact.  
**Use**: Required for Collection, Optional for Artifact, Layer, and Model  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Phone Number  
**Description**: Work phone number for the responsible point of contact.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Contact Role  
**Description**: The role(s) of the point of contact toward the digital object and its management.  
**Use**: Conditionally Required  
**Use Condition**: Contact Name  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/contact_role_terms.csv  

### Coverage
**Field Name**: Placename or Locality  
**Description**: Placename from GeoNames (http://www.geonames.org).  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text or Controlled Terms  
**Controlled Terms URL**: http://www.geonames.org  

**Field Name**: Scale  
**Description**: The scale of the dataset   
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/scale_range.csv  

**Field Name**: Spatial Extent (Decimal Degrees)  
**Description**: Coordinates for the bounding box describing the spatial extent covered by the digital object, in decimal degrees.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Array: Decimal Degrees or Geometry: Polygon  
**Controlled Terms URL**: None  

**Field Name**: Time Period Covered  
**Description**: Time period to which the data refer as a single date-time or an interval. Must conform to the ISO 8601 standard. This reflects the time period covered by the data, not the dates of coding or making documents machine-readable or the dates the data were collected. Also known as the "span" covered by the data, this may reflect the dates during which an event occured.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Date: ISO 8601  
**Controlled Terms URL**: None  

### Discovery
**Field Name**: Model Dimension  
**Description**: Dimensionality choice of a terrain model (1D, 2D, 3D, or combos) created prior to running hydro model computations.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/model_dimension_terms.csv  

**Field Name**: Boundary Type  
**Description**: The type of geospatial boundary associated with the digital object.   
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/boundary_type_terms.csv  

**Field Name**: Boundary Unit Identifier  
**Description**: The unique identifier for a geospatial boundary unit of a particular type, such as a name or code.  
**Use**: Conditionally Required  
**Use Condition**: Boundary Type  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/boundary_type_terms.csv  

**Field Name**: Creator  
**Description**: The name of a person or organization who should be cited as contributing to the initial creation of the digital object. Also referred to as an "author" or "contributor".  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Description   
**Description**: An account of the digital object. The description may include an abstract, a table of contents, or a free-text account.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Keyword Term  
**Description**: Subject matter keywords from the vocabulary chosen in Keyword Vocabulary.  
**Use**: Required  
**Use Condition**: Keyword Vocabulary  
**Accepts Multiple Values**: Yes  
**Format**: Array:Text  
**Controlled Terms URL**: None  

**Field Name**: Keyword Vocabulary  
**Description**: Vocabulary for subject matter keywords listed in Keyword Term.  
**Use**: Conditionally Required  
**Use Condition**: Keyword Terms  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/keyword_vocabulary_terms.csv  

**Field Name**: Model Type  
**Description**: The type of model.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/model_type_terms.csv  

**Field Name**: Purpose  
**Description**: A description of the purpose for the creation of this digital object and/or the expected use.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

**Field Name**: Software Name  
**Description**: The name of the software used to create or work with the digital object.  
**Use**: Required for Model, Optional for Artifact, Layer  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/software_terms.csv  

**Field Name**: Software Version  
**Description**: The version of the software used to create or work with the digital object.  
**Use**: Required for Model, Optional for Artifact, Layer  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Numeric  
**Controlled Terms URL**: None  

**Field Name**: Title  
**Description**: A name given to the digital object.  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Text  
**Controlled Terms URL**: None  

### Reuse
**Field Name**: Chain of Custody  
**Description**: A statement of any changes in ownership and custody of the digital object since its creation that are significant for its authenticity, integrity, and interpretation. The statement may include a description of any changes successive custodians made to the digital object.  
**Use**: Recommended  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: Text  
**Controlled Terms URL**: None  

## Model Configuration
### Administrative
**Field Name**: Version  
**Description**: Version number of the digital object.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: None  
**Controlled Terms URL**: None  

### Reuse
**Field Name**: Input File  
**Description**: The TDIS unique identifier for an Artifact or Layer serving as input.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: TDIS Identifier: UUID  
**Controlled Terms URL**: None  

**Field Name**: Output File  
**Description**: The TDIS unique identifier for an Artifact or Layer serving as output.  
**Use**: Optional  
**Use Condition**: None  
**Accepts Multiple Values**: Yes  
**Format**: TDIS Identifier: UUID  
**Controlled Terms URL**: None  

## Spatial Data Type
### Discovery
**Field Name**: Spatial Data Type  
**Description**: The type of spatial data  
**Use**: Required  
**Use Condition**: None  
**Accepts Multiple Values**: No  
**Format**: Controlled Terms  
**Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/spatial_data_type.csv
