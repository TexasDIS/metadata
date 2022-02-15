# TDIS Metadata and Data Assessment
This repository contains public documentation of the TDIS metadata schema under ongoing development.
**Please note**: field definitions will become more rigorous over time, and TDIS controlled terms are expected to expand as lists or hierarchies of valid terms.   

This repository also contains working data quality assessment documentation undergoing development. TDIS data quality standards will be established based on this documentation. Feedback from the community is encouraged to refine expectations.

## Metadata Organization
Within the current TDIS model, "datasets" contain "artifacts", "data layers", and "models." Data layers can also contain "features", and models can have an associated "configuration". Datasets, artifacts, data layers, features, models, and configurations each have descriptive metadata associated with them.  

![TDIS Model Diagram](https://github.com/TexasDIS/metadata/blob/main/visuals/tdis-model-diagram.png)

Datasets group one or more layers, artifacts and/or models together. For example, a complex geospatial database object would be represented as a dataset containing multiple data layers.

Artifacts represent digital objects such as content within documents, data within spreadsheets, or other data made available via service endpoints. Artifacts do not contain geometry information (points, lines, or polygons) or images with spatial information. 

Data layers represent digital objects with intrinsic spatial characteristics and include (but are not limited to) streets, city boundaries, river gages, and imagery with geospatial information contained within files or made available via service endpoints. 

Features, as a part of a data layer, are a record-by-record description of each independent “row” in a geospatial attribute table or database. 

Models represent model software packages and configurations, which may be associated with input and/or output artifacts or data layers. Model configurations represent a unique way of running a model, exposing concrete inputs, outputs, and parameters. These metadata are under active development.

## Documentation in this Repository

For a human-readable description of metadata fields, see: [tdis_metadata_field_documentation.md](https://github.com/TexasDIS/metadata/blob/main/tdis_metadata_field_documentation.md)

For CSV files containing metadata field definitions according to level/tier, see: [fields_by_level](https://github.com/TexasDIS/metadata/tree/main/fields_by_level)

For CSV files containing controlled terms for particular metadata fields, see: [controlled_terms](https://github.com/TexasDIS/metadata/tree/main/controlled_terms)

For examples and templates showing use of TDIS metadata fields, see: [examples_and_templates](https://github.com/TexasDIS/metadata/tree/main/examples_and_templates)

For documentation regarding data quality assessment, see: [data_quality_assessment](https://github.com/TexasDIS/metadata/tree/main/data_quality_assessment)
