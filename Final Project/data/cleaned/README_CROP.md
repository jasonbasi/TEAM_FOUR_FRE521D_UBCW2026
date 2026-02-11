# Data Lineage Documentation

Generated: 2026-02-10T19:13:36.068903

## Source
- File: crop_production_1990_2023.csv

## Raw Layer
- File: Not saved, dataframe only
- Contains exact copy of source with metadata columns added

## Cleaned Layer
- File: Not saved, dataframe only

## Transformations Applied
- Converted all column names to lowercase
- Stripped whitespace from text columns
- Converted Year from string to integer
- Replaced missing codes (NA, .., -, N/A) with NULL
- Created a country_id column by mapping country names to IDs
- Inserted cleaned data into MySQL crop_production table
