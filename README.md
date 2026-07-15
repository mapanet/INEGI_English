# INEGI Territorial Data Import — INEGI

## Objective

This repository contains the official procedures used to import, normalize, and prepare datasets from INEGI, AGEEML, CONAPO, and the 2020 Census, with the goal of enriching the territorial layers of **Boundaries** with reliable demographic and geographic information.

The scripts and documents inside /docs describe step‑by‑step how to obtain:

- Population by locality (2020 Census)
- Population by AGEB (2020 Census)
- Total and occupied dwellings
- Official localities (AGEEML 2026)
- Normalized municipality and state names
- CONAPO population projections 2020–2026
- Population growth from the 2020 Census to the present
- Territorial metadata for integration with Boundaries

These datasets are used to enrich the Boundaries table (colonia delimitation) created in the repository:
https://github.com/mapanet/NSE

- Layer 6 — Colonias
- Layer 5 — Cities
- Layer 2 — Municipalities
- Layer 1 — States

## Documentation Index

[01 Import INEGI Census 2020 (locality level)](docs/01_Import_INEGI_Census_2020_locality.md) 

- Total population
- Total dwellings
- Occupied dwellings
- Locality, municipality, and state codes

[02 Import_INEGI_Cenus_2020_AGEB](docs/02_Import_INEGI_Census_2020_AGEB.md)   

- Population by AGEB
- Total and occupied dwellings
- Key demographic variables
- CVEGEO normalization
- Used for AGEB ↔ colonia interpolation (NSE and population)
  
[03 Import_Localidades_2025 Catalog](docs/03_Import_Localities_2025.md)   

- Official locality names
- Municipality and state codes
- Locality type (urban/rural)
- Integration with Boundaries for territorial labeling
- Base dataset for rural fallback in NSE

[04 Import_AGEEML_2026](docs/04_Import_AGEEML_2026.md)   

AGEEML 2026 import (Localities and Municipalities):

- Official municipality and state names
- Normalized keys
- Updated 2026 locality catalog
- Territorial base for Boundaries
- Correction of names and metadata in Layers 1–5

[05 Import Population Proyections CONAPO 2020–2026](docs/05_Import_CONAPO_Population.md) 

- Estimated population by municipality
- Annual growth
- Projection from Census 2020 to 2026
- Updated population calculation for Boundaries
- Integration with municipal and state layers

## Repository Purpose

This repository exists to:

1. Centralize all official data import procedures

```code
INEGI, AGEEML, CONAPO, and Census 2020.
```

2. Normalize territorial keys

- CVEGEO
- Locality codes
- Municipality codes
- State codes

3. Generate consistent datasets for Boundaries (colonias), including:

- Population
- Dwellings
- Occupied_Dwellings
- Growth_2020_2026
- Locality
- Municipality
- State

4. Maintain traceability and reproducibility

Each document explains:

- Official source
- Import steps
- Normalization
- Validations
- Integration with SQL and geoprocessing

5. Serve as the foundation for larger pipelines, such as:

- NSE AMAI by colonia (https://github.com/mapanet/NSE_English)
- Municipal population growth
- Territorial layer updates

## Integration with Boundaries

The imported datasets feed:

**Layer 6 — Colonias**
AGEB ↔ colonia interpolation for population and dwellings.

**Layer 5 — Cities**
Aggregation by locality and municipality.

**Layer 2 — Municipalities**
Population updated using CONAPO projections.

**Layer 1 — States**
State-level aggregation and AGEEML metadata.



CVEGEO and territorial key normalization

Used to enrich Boundaries with locality-level population
