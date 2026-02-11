# Data Lineage Documentation

Generated: 2026-02-10T19:13:36.069219

## Source
- File: temperature_anomalies_1990_2023.csv

## Raw Layer
- File: Not saved, dataframe only
- Contains exact copy of source with metadata columns added

## Cleaned Layer
- File: Not saved, dataframe only

## Transformations Applied
- Converted all column names to lowercase
- Stripped whitespace from text columns
- Created country_std for mapping to countries table
- Converted numeric columns to float (handled European decimals)
- Converted Year from string to integer
- Converted monthly anomaly columns to float (handled European decimals)
- Renamed month columns to match DB schema (e.g., 'january' to 'jan')
- Replaced missing codes (NA, .., -, N/A) with NULL
- Inserted cleaned data into MySQL temperature_anomalies table
