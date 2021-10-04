#TDIS Metadata Documentation
*Last revised: 2021-10-04*

## Metadata Organization
Within the current TDIS model, "datasets" contain "artifacts" and "data layers." Data layers can also contain "features". Datasets, artifacts, data layers, and features, each have descriptive metadata records associated with them.

![TDIS Model Diagram](https://github.com/TexasDIS/metadata/blob/main/visuals/tdis-model-diagram.png)

Artifacts represent digital objects, such as model software, content within documents, data within spreadsheets, or other data made available via service endpoints. Artifacts do not contain geometry information (points, lines, or polygons) or images with spatial information. 

Data layers have intrinsic spatial characteristics and include (but are not limited to) streets, city boundaries, river gages, and imagery with geospatial information contained within files or made available via service endpoints. 

Features, as a part of a data layer, are a record-by-record description of each independent “row” in an geospatial attribute table or database. 

### Field Definition Glossary 
Each metadata field below is defined with the following elements:

- **Field Name**: A display name for the metadata field.
- **Description**: Text describing the information that the metadata field should contain as a value. 
- **Use**: An indication of whether the metadata field is "Required", "Recommended", "Optional", "Conditionally Required", or "Conditionally Recommended" within the level (e.g. Dataset, Artifact, Data Layer, Feature).
- **Condition**: The condition dictating when a "Conditionally Required" metadata field becomes "Required", or a "Conditionally Recommended" metadata field becomes "Recommended". "None" indicates that there are no conditions.
- **Accepts Multiple Values**: "Yes" or "No" indicating that multiple values can be added to the metadata field.
- **Format**: Indication of the type of value the field takes, this will be used for validation.
- **Controlled Terms URL**: A link to published terms that are valid.

## Artifact
### Access
- **Field Name**: Distribution Method
- **Description**: Description of the digital method of distribution.
- **Use**: Conditionally Required
- **Use Condition**: Distributor or Publisher
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Distributor or Publisher
- **Description**: The organization sharing, publishing, or otherwise responsible for providing access to the resource.
- **Use**: Conditionally Required
- **Use Condition**: Distribution URL
- **Accepts Multiple Values**: No
- **Format**: Text or Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Service Endpoint Type
- **Description**: The type of service endpoint used for distribution.
- **Use**: Conditionally Required
- **Use Condition**: Service Endpoint URL
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Service Endpoint URL
- **Description**: URL of the service endpoint, API, etc.
- **Use**: Conditionally Required
- **Use Condition**: Service Endpoint Type
- **Accepts Multiple Values**: No
- **Format**: URL
- **Controlled Terms URL**: None

### Administrative
- **Field Name**: Date Last Updated
- **Description**: Date the resource was last updated, or creation date if no updates have been made, YYYY-MM-DD or YYYY-MM or YYYY.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Date: ISO 8601
- **Controlled Terms URL**: None

- **Field Name**: License
- **Description**: License associated with the resource.
- **Use**: Optional
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Metadata Date
- **Description**: Date the metadata record was last updated.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Date: ISO 8601
- **Controlled Terms URL**: None

- **Field Name**: Update Frequency
- **Description**: If the data are regularly updated, how often.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/update_frequency_terms.csv

- **Field Name**: Use Constraint
- **Description**: Constraints or restrictions on use of the resource.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/use_constraint_terms.csv

- **Field Name**: Version
- **Description**: Version number of the resource.
- **Use**: Optional
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: TBD
- **Controlled Terms URL**: None

### Contact Information
- **Field Name**: Contact Affiliation
- **Description**: Organizational affiliation for the responsible point of contact.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Text or Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Contact Cell Phone
- **Description**: Cell phone number for the responsible point of contact.
- **Use**: Conditionally Required
- **Use Condition**: Contact Name
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Contact Email
- **Description**: Email for the responsible point of contact.
- **Use**: Conditionally Required
- **Use Condition**: Contact Name
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Contact Name
- **Description**: Name of the responsible point of contact.
- **Use**: Required for Dataset, Optional at lower levels
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Contact Role
- **Description**: The role or responsibility of the point of contact.
- **Use**: Conditionally Required
- **Use Condition**: Contact Name
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Contact Work Phone
- **Description**: Work phone number for the responsible point of contact.
- **Use**: Conditionally Required
- **Use Condition**: Contact Name
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

### Coverage
- **Field Name**: Placename or Locality
- **Description**: Placename from GeoNames (http://www.geonames.org).
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Text or Controlled Terms
- **Controlled Terms URL**: http://www.geonames.org

- **Field Name**: Spatial Extent (Decimal Degrees)
- **Description**: Coordinates for the bounding box describing the extent of the resource in decimal degrees.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Array: Decimal Degrees or Geometry: Polygon
- **Controlled Terms URL**: None

- **Field Name**: Time Period Covered
- **Description**: Time period to which the data refer as a single date/time, multiple dates/times, or a range of dates/times in ISO 8601. This reflects the time period covered by the data, not the dates of coding or making documents machine-readable or the dates the data were collected. Also known as span.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Date: ISO 8601
- **Controlled Terms URL**: None

### Discovery
- **Field Name**: Classification Term
- **Description**: TBD
- **Use**: TBD
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Classification Type
- **Description**: TBD
- **Use**: TBD
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Description 
- **Description**: An account of the resource. Description may include but is not limited to: an abstract, a table of contents, or a free-text account of the resource.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Digital Object Type
- **Description**: The type of content in the resource and optionally format. For files uploaded to TDIS/
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/object_type_terms.csv

- **Field Name**: Keyword Term
- **Description**: Subject matter keywords from the vocabulary chosen in Keyword Vocabulary.
- **Use**: Conditionally Required
- **Use Condition**: Keyword Vocabulary
- **Accepts Multiple Values**: Yes
- **Format**: Array:Text
- **Controlled Terms URL**: None

- **Field Name**: Keyword Vocabulary
- **Description**: Vocabulary for subject matter keywords listed in Keyword Term.
- **Use**: Conditionally Required
- **Use Condition**: Keyword Terms
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/keyword_vocabulary_terms.csv

- **Field Name**: Purpose
- **Description**: Purpose for the creation of this resource and/or expected use.
- **Use**: Optional
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Title
- **Description**: A name given to the resource.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

### Reuse
- **Field Name**: Collection Method
- **Description**: The procedure, technique, or mode of inquiry used to attain data.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/collection_method_terms.csv

- **Field Name**: Processing Step Date
- **Description**: The date when a particular processing step was completed, YYYY-MM-DD or YYYY-MM or YYYY. 
- **Use**: Optional
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Date: ISO 8601
- **Controlled Terms URL**: None

- **Field Name**: Processing Step Description
- **Description**: Description of the processing step performed on a date. A processing step represents a structural change to the data (such as adding fields) and not the addition of data. There can be several processing steps, each of which may have a different date.
- **Use**: Conditionally Required
- **Use Condition**: Processing Step Date
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

## Dataset
### Administrative
- **Field Name**: License
- **Description**: License associated with the resource.
- **Use**: Optional
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Metadata Date
- **Description**: Date the metadata record was last updated.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Date: ISO 8601
- **Controlled Terms URL**: None

- **Field Name**: Use Constraint
- **Description**: Constraints or restrictions on use of the resource.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/use_constraint_terms.csv

### Contact Information
- **Field Name**: Contact Affiliation
- **Description**: Organizational affiliation for the responsible point of contact.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Text or Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Contact Email
- **Description**: Email for the responsible point of contact.
- **Use**: Conditionally Required
- **Use Condition**: Contact Name
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Contact Name
- **Description**: Name of the responsible point of contact.
- **Use**: Required for Dataset, Optional at lower levels
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Contact Role
- **Description**: The role or responsibility of the point of contact.
- **Use**: Conditionally Required
- **Use Condition**: Contact Name
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: TBD

### Coverage
- **Field Name**: Spatial Extent (Decimal Degrees)
- **Description**: Coordinates for the bounding box describing the extent of the resource in decimal degrees.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Array: Decimal Degrees or Geometry: Polygon
- **Controlled Terms URL**: None

### Discovery
- **Field Name**: Description 
- **Description**: An account of the resource. Description may include but is not limited to: an abstract, a table of contents, or a free-text account of the resource.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Keyword Term
- **Description**: Subject matter keywords from the vocabulary chosen in Keyword Vocabulary.
- **Use**: Conditionally Required
- **Use Condition**: Keyword Vocabulary
- **Accepts Multiple Values**: Yes
- **Format**: Array:Text
- **Controlled Terms URL**: None

- **Field Name**: Keyword Vocabulary
- **Description**: Vocabulary for subject matter keywords listed in Keyword Term.
- **Use**: Conditionally Required
- **Use Condition**: Keyword Terms
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/keyword_vocabulary_terms.csv

- **Field Name**: Purpose
- **Description**: Purpose for the creation of this resource and/or expected use.
- **Use**: Optional
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Title
- **Description**: A name given to the resource.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

### Reuse
- **Field Name**: Provenance
- **Description**: A statement of any changes in ownership and custody of the resource since its creation that are significant for its authenticity, integrity, and interpretation. The statement may include a description of any changes successive custodians made to the resource.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

## Feature
### Administrative
- **Field Name**: Date Last Updated
- **Description**: Date the resource was last updated, or creation date if no updates have been made, YYYY-MM-DD or YYYY-MM or YYYY.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Date: ISO 8601
- **Controlled Terms URL**: None

### Coverage
- **Field Name**: Area (Square Meters)
- **Description**: Numeric value for the area of the feature in square meters.
- **Use**: Conditionally Required
- **Use Condition**: Spatial Extent: None
- **Accepts Multiple Values**: No
- **Format**: Numeric
- **Controlled Terms URL**: None

- **Field Name**: Length (Meters)
- **Description**: Numeric value for the length dimension of the feature in meters.
- **Use**: Conditionally Recommended
- **Use Condition**: Spatial Extent: None
- **Accepts Multiple Values**: No
- **Format**: Numeric
- **Controlled Terms URL**: None

- **Field Name**: Spatial Extent (Decimal Degrees)
- **Description**: Coordinates for the bounding box describing the extent of the resource in decimal degrees.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Array: Decimal Degrees or Geometry: Polygon
- **Controlled Terms URL**: None

- **Field Name**: Width (Meters)
- **Description**: Numeric value for the width dimension of the feature in meters.
- **Use**: Conditionally Recommended
- **Use Condition**: Spatial Extent: None
- **Accepts Multiple Values**: No
- **Format**: Numeric
- **Controlled Terms URL**: None

### Reuse
- **Field Name**: Horizontal Accuracy Method
- **Description**: Method for determining accuracy of the data.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: TBD
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Vertical Accuracy Method
- **Description**: Method for determining accuracy of the data.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: TBD
- **Format**: Text
- **Controlled Terms URL**: None

## Layer
### Access
- **Field Name**: Distribution Method
- **Description**: Description of the digital method of distribution.
- **Use**: Conditionally Required
- **Use Condition**: Distributor or Publisher
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Distributor or Publisher
- **Description**: The organization sharing, publishing, or otherwise responsible for providing access to the resource.
- **Use**: Conditionally Required
- **Use Condition**: Distribution URL
- **Accepts Multiple Values**: No
- **Format**: Text or Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Service Endpoint Type
- **Description**: The type of service endpoint used for distribution.
- **Use**: Conditionally Required
- **Use Condition**: Service Endpoint URL
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Service Endpoint URL
- **Description**: URL of the service endpoint, API, etc.
- **Use**: Conditionally Required
- **Use Condition**: Service Endpoint Type
- **Accepts Multiple Values**: No
- **Format**: URL
- **Controlled Terms URL**: None

### Administrative
- **Field Name**: Date Last Updated
- **Description**: Date the resource was last updated, or creation date if no updates have been made, YYYY-MM-DD or YYYY-MM or YYYY.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Date: ISO 8601
- **Controlled Terms URL**: None

- **Field Name**: Metadata Date
- **Description**: Date the metadata record was last updated.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Date: ISO 8601
- **Controlled Terms URL**: None

- **Field Name**: Update Frequency
- **Description**: If the data are regularly updated, how often.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/update_frequency_terms.csv

- **Field Name**: Use Constraint
- **Description**: Constraints or restrictions on use of the resource.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/use_constraint_terms.csv

### Contact Information
- **Field Name**: Contact Affiliation
- **Description**: Organizational affiliation for the responsible point of contact.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Text or Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Contact Email
- **Description**: Email for the responsible point of contact.
- **Use**: Conditionally Required
- **Use Condition**: Contact Name
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Contact Name
- **Description**: Name of the responsible point of contact.
- **Use**: Required for Dataset, Optional at lower levels
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Contact Role
- **Description**: The role or responsibility of the point of contact.
- **Use**: Conditionally Required
- **Use Condition**: Contact Name
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: TBD

### Coverage
- **Field Name**: Placename or Locality
- **Description**: Placename from GeoNames (http://www.geonames.org).
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Text or Controlled Terms
- **Controlled Terms URL**: http://www.geonames.org

- **Field Name**: Spatial Extent (Decimal Degrees)
- **Description**: Coordinates for the bounding box describing the extent of the resource in decimal degrees.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Array: Decimal Degrees or Geometry: Polygon
- **Controlled Terms URL**: None

- **Field Name**: Time Period Covered
- **Description**: Time period to which the data refer as a single date/time, multiple dates/times, or a range of dates/times in ISO 8601. This reflects the time period covered by the data, not the dates of coding or making documents machine-readable or the dates the data were collected. Also known as span.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Date: ISO 8601
- **Controlled Terms URL**: None

### Discovery
- **Field Name**: Classification Term
- **Description**: TBD
- **Use**: TBD
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Classification Type
- **Description**: TBD
- **Use**: TBD
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: TBD

- **Field Name**: Description 
- **Description**: An account of the resource. Description may include but is not limited to: an abstract, a table of contents, or a free-text account of the resource.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Digital Object Type
- **Description**: The type of content in the resource and optionally format. For files uploaded to TDIS/
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/object_type_terms.csv

- **Field Name**: Keyword Term
- **Description**: Subject matter keywords from the vocabulary chosen in Keyword Vocabulary.
- **Use**: Conditionally Required
- **Use Condition**: Keyword Vocabulary
- **Accepts Multiple Values**: Yes
- **Format**: Array:Text
- **Controlled Terms URL**: None

- **Field Name**: Keyword Vocabulary
- **Description**: Vocabulary for subject matter keywords listed in Keyword Term.
- **Use**: Conditionally Required
- **Use Condition**: Keyword Terms
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/keyword_vocabulary_terms.csv

- **Field Name**: Purpose
- **Description**: Purpose for the creation of this resource and/or expected use.
- **Use**: Optional
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Title
- **Description**: A name given to the resource.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Text
- **Controlled Terms URL**: None

### Reuse
- **Field Name**: Attribute Description
- **Description**: Description of the attribute (field, variable) within the attribute table for this layer.
- **Use**: Optional
- **Use Condition**: TBD
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Attribute Domain Type
- **Description**: Domain for values in the attribute (field, variable) within the attribute table.
- **Use**: Optional 
- **Use Condition**: TBD
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/geo_attribute_value_type_terms.csv

- **Field Name**: Attribute Name
- **Description**: Name of the attribute (field, variable) within the attribute table for this layer.
- **Use**: Optional
- **Use Condition**: TBD
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Code Set URL
- **Description**: URL for the published code set.
- **Use**: Conditionally Required
- **Use Condition**: Attribute Domain Type: Published Code Set
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Collection Method
- **Description**: The procedure, technique, or mode of inquiry used to attain data.
- **Use**: Recommended
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://github.com/TexasDIS/metadata/blob/main/controlled_terms/collection_method_terms.csv

- **Field Name**: Domain Value
- **Description**: Valid value for the attribute.
- **Use**: Conditionally Required
- **Use Condition**: Attribute Domain Type: Enumerated List
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Domain Value Description
- **Description**: Description of the valid value for the attribute.
- **Use**: Conditionally Recommended
- **Use Condition**: Attribute Domain Type: Enumerated List
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Horizontal Accuracy (Meters)
- **Description**: Numeric value for the accuracy in meters.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: TBD
- **Format**: Numeric
- **Controlled Terms URL**: None

- **Field Name**: Horizontal Accuracy Method
- **Description**: Method for determining accuracy of the data.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: TBD
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Horizontal Coordinate System
- **Description**: TBD
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://spatialreference.org/ref/

- **Field Name**: Horizontal Datum
- **Description**: A horizontal datum is a specified coordinate system for a collection of positions on the surface of the earth. 
- **Use**: TBD
- **Use Condition**: TBD
- **Accepts Multiple Values**: TBD
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://www.ngs.noaa.gov/datums/horizontal/

- **Field Name**: Processing Step Date
- **Description**: The date when a particular processing step was completed, YYYY-MM-DD or YYYY-MM or YYYY. 
- **Use**: Optional
- **Use Condition**: None
- **Accepts Multiple Values**: Yes
- **Format**: Date: ISO 8601
- **Controlled Terms URL**: None

- **Field Name**: Processing Step Description
- **Description**: Description of the processing step performed on a date. A processing step represents a structural change to the data (such as adding fields) and not the addition of data. There can be several processing steps, each of which may have a different date.
- **Use**: Conditionally Required
- **Use Condition**: Processing Step Date
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Value Range
- **Description**: Range of valid values separated by a dash ("-").
- **Use**: Conditionally Required
- **Use Condition**: Attribute Domain Type: Range
- **Accepts Multiple Values**: Yes
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Vertical Accuracy (Meters)
- **Description**: Numeric value for the accuracy in meters.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: TBD
- **Format**: Numeric
- **Controlled Terms URL**: None

- **Field Name**: Vertical Accuracy Method
- **Description**: Method for determining accuracy of the data.
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: TBD
- **Format**: Text
- **Controlled Terms URL**: None

- **Field Name**: Vertical Coordinate System
- **Description**: TBD
- **Use**: Required
- **Use Condition**: None
- **Accepts Multiple Values**: No
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://spatialreference.org/ref/

- **Field Name**: Vertical Datum
- **Description**: A vertical datum is a surface of zero elevation to which heights of various points are referenced. 
- **Use**: TBD
- **Use Condition**: TBD
- **Accepts Multiple Values**: TBD
- **Format**: Controlled Terms
- **Controlled Terms URL**: https://www.ngs.noaa.gov/datums/vertical/

