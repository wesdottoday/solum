# Solum: Data Sources

Every dataset used in Solum's training corpus, its provider, license, and what it contains. This file is the authoritative reference for what data Solum uses and under what terms.

For our data collection principles, see the [Data Principles](README.md#data-principles) section of the README.

---

## Approved Sources

These sources have clear licensing and are approved to enter the training pipeline.

### Soil Data

| Source | Provider | License | Data Type | Coverage | Resolution |
|--------|----------|---------|-----------|----------|------------|
| **gNATSGO** | USDA NRCS via Microsoft Planetary Computer | US Public Domain | Tabular soil survey: texture, organic matter, pH, CEC, drainage, crop yields, native plants, engineering properties | United States (complete) | Sub-field (soil map unit) |
| **ISRIC WoSIS** | ISRIC: World Soil Information | CC-BY 4.0 | Measured soil profiles: organic carbon, nitrogen, pH, texture, CEC, bulk density | Global (228K profiles, 118+ countries) | Point data |
| **iSDA Soil** | Innovative Solutions for Decision Agriculture | CC-BY 4.0 | Predicted soil properties: pH, organic carbon, texture, bulk density, CEC, nutrients | Continental Africa | 30 m |
| **ISRIC SoilGrids 250m** | ISRIC: World Soil Information | CC-BY 4.0 | Global predictions of 14 soil properties at 6 standard depth intervals, machine-learning based | Global | 250 m |
| **OSSL** | ISRIC / OpenGeoHub Foundation via Zenodo | CC-BY 4.0 | Soil spectral library: 91K MIR + 65K VisNIR scans paired with wet chemistry | Global (60K+ locations) | Point data |

### Climate Data

| Source | Provider | License | Data Type | Coverage | Resolution |
|--------|----------|---------|-----------|----------|------------|
| **WorldClim v2.1** | UC Davis / WorldClim consortium | CC-BY-SA 4.0 | 19 bioclimatic variables + monthly temperature, precipitation, solar radiation, wind, vapor pressure, elevation | Global | ~1 km |

### Plant and Species Data

| Source | Provider | License | Data Type | Coverage | Resolution |
|--------|----------|---------|-----------|----------|------------|
| **USDA PLANTS** | USDA NRCS | US Public Domain | 90,798 species: taxonomy, native range, growth characteristics (94 fields), ethnobotany, pollinator data, wildlife value, wetland indicators | United States and territories | Species-level |
| **USDA PLANTS Fact Sheets** | USDA NRCS | US Public Domain | 629 detailed species profiles: planting guidance, establishment, management, pests | United States | Species-level |
| **GBIF** | Global Biodiversity Information Facility | CC0 1.0 | Species occurrence records with coordinates for 12 agriculture-relevant plant families + 15 key cover crop and agroforestry species | Global | Point data |

### Land Cover

| Source | Provider | License | Data Type | Coverage | Resolution |
|--------|----------|---------|-----------|----------|------------|
| **Copernicus Global Land Cover** | European Commission / Copernicus | Free for any purpose (Copernicus data policy) | 23-class land cover classification with probability layers | Global | 100 m |

### Research and Practitioner Knowledge

| Source | Provider | License | Data Type | Coverage | Resolution |
|--------|----------|---------|-----------|----------|------------|
| **SARE Reports** | USDA Sustainable Agriculture Research and Education | US Public Domain | 7,756 on-farm research reports: practices tested, outcomes, budgets, farmer-researcher partnerships | United States (all regions) | Farm-level |
| **SARE Publications** | USDA SARE | US Public Domain | 3,260 PDFs: fact sheets, bulletins, technical guides on cover crops, soil health, organic production | United States | Regional to national |
| **SARE Books** | USDA SARE | US Public Domain | 3 flagship books: *Building Soils for Better Crops*, *Managing Cover Crops Profitably*, *Cover Crops for All Seasons* | United States | National |
| **Internet Archive USDA** | Internet Archive (hosting USDA publications) | US Public Domain | 1,076 historical agriculture texts: Soil Conservation Service publications, USDA yearbooks, experiment station reports (1880s-1970s) | United States | National to regional |
| **MDPI Soil Systems** | MDPI | CC-BY 4.0 | Open access peer-reviewed soil science journal papers | International | N/A |
| **Army Corps Wetland Manuals** | US Army Corps of Engineers | US Public Domain | Federal wetland delineation manual + 6 regional supplements: hydric soil indicators, wetland identification criteria | United States (by ecoregion) | Site-level |
| **ATTRA/NCAT** | National Center for Appropriate Technology (USDA-funded) | US Public Domain | Practical sustainable agriculture guides: organic farming, soil health, pest management | United States | National |

---

## Excluded

| Source | Reason |
|--------|--------|
| **FAOSTAT** | CC-BY-NC-SA 3.0 IGO: non-commercial clause requires separate confirmation from FAO for training use |
| **PFAF (Plants for a Future)** | Ambiguous licensing for AI training: replaced with USDA PLANTS |
| **Copyrighted books** | Core regenerative agriculture reading list: not licensed for training |
| **Podcast/YouTube transcripts** | Require creator permission |
| **China national soil data** | Foreign access restricted |
| **Cranfield/NSRI UK soil data** | IP retained by Cranfield, commercial licensing required |
| **Semantic Scholar abstracts** | API terms unclear for AI training use |
| **FAO HWSD / GSOCmap** | License terms not explicitly stated for AI training: covered by ISRIC WoSIS and SoilGrids with clear CC-BY 4.0 licensing |
| **Rodale FST report** | No explicit license for training use: findings available through approved SARE and journal sources |

---

## License Key

| Identifier | Description | Training Use |
|------------|-------------|-------------|
| US Public Domain | US government works, not subject to copyright | Unrestricted |
| CC0 1.0 | Public domain dedication | Unrestricted |
| CC-BY 4.0 | Attribution required | OK: attribution maintained in source catalog |
| CC-BY-SA 4.0 | Attribution + share-alike | OK: model released under compatible share-alike terms |
| CC-BY-NC 4.0 | Attribution + non-commercial | OK: Solum is a non-commercial project |
| Copernicus Data Policy | Free for any purpose with attribution | OK: attribution maintained |
