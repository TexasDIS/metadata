# TDIS Metadata
This repository contains public documentation of the TDIS metadata schema under ongoing development. 
Please note that field definitions will become more rigorous over time, and TDIS controlled vocabularies are expected to expand as lists or hierarchies of valid terms.

## Metadata Organization
Within the current TDIS model, "datasets" contain "artifacts" and "data layers." Data layers can also contain "features". Datasets, artifacts, data layers, and features, each have descriptive metadata records associated with them.

![TDIS Model Diagram](https://github.com/TexasDIS/metadata/blob/main/visuals/tdis-model-diagram.png)

Artifacts represent digital objects, such as model software, content within documents, data within spreadsheets, or other data made available via service endpoints. Artifacts do not contain geometry information (points, lines, or polygons) or images with spatial information. 

Data layers have intrinsic spatial characteristics and include (but are not limited to) streets, city boundaries, river gages, and imagery with geospatial information contained within files or made available via service endpoints. 

Features, as a part of a data layer, are a record-by-record description of each independent “row” in a geospatial attribute table or database. 

## Documentation in this Repository

For a human-readable description of metadata fields, see: [tdis_metadata_field_documentation.md](https://github.com/TexasDIS/metadata/blob/main/tdis_metadata_field_documentation.md)

For CSV files containing metadata field definitions according to level/tier, see: [fields_by_level](https://github.com/TexasDIS/metadata/tree/main/fields_by_level)
