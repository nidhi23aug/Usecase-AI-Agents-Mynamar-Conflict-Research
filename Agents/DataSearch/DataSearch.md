# Data Search for these research question:

Use - https://platform.openai.com/agent-builder/edit?version=draft&workflow=wf_6949ac60e244819082e6ed0bf22ccead09adcd4d789b8c37

Input---> these are the research questions based from Gap Agent:
RQ1 — What is the spatiotemporal pattern of cropland abandonment and recultivation in the Myanmar conflict region?
H₀: No detectable change in abandonment/recultivation rates across conflict vs non-conflict periods/areas.
H₁: Abandonment/recultivation rates show detectable temporal shifts aligned with conflict escalation/de-escalation.

Variables/proxies (RS): annual (or seasonal) cropland state; abandonment onset year; recultivation onset year; duration distributions (per pixel/object).

RQ2 — How ephemeral is “conflict-linked” abandonment: what are the duration distributions and recultivation half-lives?
H₀: Abandonment persistence does not differ from non-conflict benchmark areas/time.
H₁: Abandonment persistence differs (shorter or longer) in conflict-affected areas.
---

Query 1--> What is the spatiotemporal pattern of cropland abandonment and recultivation in the Myanmar conflict region?

User selection- Higher resolution, Year 2018-2024 (conflict year is 2021)

User intent (restated, no inference): Discover NASA Earthdata CMR collections that support analyzing cropland abandonment and recultivation in the Myanmar conflict region, with a preference for ~10 m spatial resolution and 2018–2025 temporal coverage.

Confirmed inputs
Phenomenon: cropland abandonment and recultivation

Spatial-resolution requirement: ~10 m

Temporal bounds: 2018-01-01 to 2025-12-31

Region: Myanmar conflict region (exact boundary not specified)

Unresolved ambiguities (treated as unknown)
Exact spatial boundary within Myanmar (state/region/polygon)

Whether SAR (radar) imagery is acceptable as “10 m-class” high-resolution input (optical 10 m Sentinel-2 style vs radar)

Candidate variable families (terms only)
Sentinel-2 reflectance / surface reflectance (10 m bands)

Land cover / cropland class maps at 10 m

Cropland activity masks (binary “active cropland” by season)

SAR GRD amplitude (dual-pol), high-resolution mapping

3. Curated / Ranked CMR Dataset List
Important metadata gap found: In this CMR discovery run, I did not find a clearly documented global Myanmar-covering optical 10 m reflectance time series continuing through 2025. Some 10 m products appear to be single-year maps (e.g., 2020/2021 land cover), while the longer 2018–2025 continuity is more clearly supported (in CMR) by Sentinel-1 SAR GRD collections (high-resolution radar; exact pixel spacing is not stated in the returned metadata snippets).

Tabular Summary (≥2 datasets)
Rank	Short Name	Concept ID	10 m stated in metadata?	Temporal coverage (metadata)	Notes (metadata-only)
1	SENTINEL-1A_DP_GRD_HIGH	C1214470533-ASF	Not stated; “down to 5 meters” capability described	2014-04-03 → ongoing	SAR GRD; supports 2018–2025 window
2	SENTINEL-1C_DP_GRD_HIGH	C3486566209-ASF	Not stated; “down to 5 meters” capability described	2025-03-28 → ongoing	SAR GRD; covers 2025 onward
3	SENTINEL-1B_DP_GRD_HIGH	C1327985645-ASF	Not stated; “down to 5 meters” capability described	2016-04-25 → 2021-12-24	SAR GRD; covers 2018–2021 portion
4	urn:eop:VITO	C2207478523-FEDEO	Partly (GSD 10/20/60 m described for L1C; TOC resolution not explicitly stated here)	2015-07-06 → 2021-12-31	Sentinel-2 L2A TOC tiles; ends 2021 in metadata
5	urn:eop:VITO	C2207478568-FEDEO	Yes (10/20/60 m GSD stated)	2015-07-06 → 2021-12-31	Sentinel-2 L1C TOA tiles; ends 2021
6	urn:eop:VITO	C2655129129-FEDEO	Yes (10 m stated)	time_start=1970 placeholder	Title indicates 2020 land cover map
7	urn:eop:VITO	C2655129178-FEDEO	Yes (10 m stated)	time_start=1970 placeholder	Title indicates 2021 land cover map
8	urn:eop:VITO	C2770608964-FEDEO	Yes (10 m stated)	time_start=1970 placeholder	Title indicates 2020 NDVI percentile composite
9	urn:eop:VITO	C2655128870-FEDEO	Yes (10 m stated)	time_start=1970 placeholder	Title indicates 2021 NDVI percentile composite
10	urn:eop:VITO	C2734302030-FEDEO	Not stated in returned metadata	time_start=1970 placeholder	Seasonal binary “active cropland” (time/resolution not provided here)
1) SENTINEL-1A_DP_GRD_HIGH (Sentinel-1A Dual Pol High-Res GRD)
Short Name: SENTINEL-1A_DP_GRD_HIGH

CMR Concept ID: C1214470533-ASF

Variables (verbatim): “Pixel values represent detected amplitude. Phase information is lost.”

Temporal Coverage (metadata): start 2014-04-03T00:00:00Z; end not returned

Spatial Coverage (metadata text): not explicitly stated in returned metadata fields

ProcessingLevelId: null

Missing/ambiguous metadata: no explicit “10 m” pixel spacing stated in returned snippet; cropland variables not present (it’s a SAR product type)

2) SENTINEL-1C_DP_GRD_HIGH (Sentinel-1C Dual Pol High-Res GRD)
Short Name: SENTINEL-1C_DP_GRD_HIGH

CMR Concept ID: C3486566209-ASF

Variables (verbatim): “Pixel values represent detected amplitude. Phase information is lost.”

Temporal Coverage (metadata): start 2025-03-28T00:00:00Z; end not returned

Spatial Coverage (metadata text): not explicitly stated in returned metadata fields

ProcessingLevelId: null

Missing/ambiguous metadata: resolution/pixel spacing not explicitly stated; only mission capability language present in summary

3) SENTINEL-1B_DP_GRD_HIGH (Sentinel-1B Dual Pol High-Res GRD)
Short Name: SENTINEL-1B_DP_GRD_HIGH

CMR Concept ID: C1327985645-ASF

Variables (verbatim): GRD detected amplitude (phase lost)

Temporal Coverage (metadata): 2016-04-25T00:00:00Z → 2021-12-24T00:00:00Z

Spatial Coverage (metadata text): not explicitly stated in returned metadata fields

ProcessingLevelId: null

Missing/ambiguous metadata: does not extend to 2025; pixel spacing not stated in returned snippet

4) SENTINEL-2 Top of Canopy (TOC) Products (tiles) - V2
Short Name: urn:eop:VITO

CMR Concept ID: C2207478523-FEDEO

Variables (verbatim): “L2A atmospheric corrected Top-Of-Canopy (TOC) products, generated using the Sen2COR processing tool.”

Temporal Coverage (metadata): 2015-07-06T00:00:00Z → 2021-12-31T23:59:00Z

Spatial Coverage (metadata text): “tiles” mentioned; geographic coverage not stated in returned metadata

ProcessingLevelId: null

Missing/ambiguous metadata: no explicit statement of 10 m in this record; does not cover 2022–2025

5) SENTINEL-2 Level1C products (TerraScope) - V2
Short Name: urn:eop:VITO

CMR Concept ID: C2207478568-FEDEO

Variables (verbatim): “Top Of Atmosphere (TOA) reflectances… resampled with a constant Ground Sampling Distance (GSD) of 10, 20 and 60 m”

Temporal Coverage (metadata): 2015-07-06T00:00:00Z → 2021-12-31T23:59:00Z

Spatial Coverage (metadata text): “100x100 km2 tiles (ortho-images in UTM/WGS84 projection)” (coverage region not stated)

ProcessingLevelId: null

Missing/ambiguous metadata: does not cover 2022–2025; geographic coverage not explicit in returned metadata

6) ESA WorldCover 10 meter Land Cover Map 2020
Short Name: urn:eop:VITO

CMR Concept ID: C2655129129-FEDEO

Variables (verbatim): “global land cover map with 11 land cover classes… worldwide coverage at 10 meters… 3 x 3 degree tile… Cloud Optimized GeoTIFFs”

Temporal Coverage (metadata): time_start returned as 1970-01-01 (placeholder; year “2020” is in the EntryTitle)

Spatial Coverage (metadata text): “worldwide coverage”

ProcessingLevelId: null

Missing/ambiguous metadata: CMR temporal fields appear inconsistent with the year stated in EntryTitle

7) ESA WorldCover 10 meter Land Cover Map 2021
Short Name: urn:eop:VITO

CMR Concept ID: C2655129178-FEDEO

Variables (verbatim): “worldwide coverage at 10 meters… 3 x 3 degree tile… Cloud Optimized GeoTIFFs”

Temporal Coverage (metadata): time_start returned as 1970-01-01 (placeholder; year “2021” is in EntryTitle)

Spatial Coverage (metadata text): “worldwide coverage”

ProcessingLevelId: null

Missing/ambiguous metadata: same temporal-field inconsistency as above

8) ESA WorldCover Sentinel-2 yearly NDVI percentiles color composite 2020, 10 meter
Short Name: urn:eop:VITO

CMR Concept ID: C2770608964-FEDEO

Variables (verbatim): “NDVI p10 / p50 / p90… generated by taking the NDVI timeseries for 2020… Worldwide coverage at 10 meters… 1 x 1 degree tile”

Temporal Coverage (metadata): time_start returned as 1970-01-01 (placeholder; “2020” in EntryTitle)

Spatial Coverage (metadata text): worldwide

ProcessingLevelId: null

Missing/ambiguous metadata: temporal fields inconsistent with year described in EntryTitle

9) ESA WorldCover Sentinel-2 yearly NDVI percentiles color composite 2021, 10 meter
Short Name: urn:eop:VITO

CMR Concept ID: C2655128870-FEDEO

Variables (verbatim): “generated by taking the NDVI timeseries for 2021… Worldwide coverage at 10 meters… 1 x 1 degree tile”

Temporal Coverage (metadata): time_start returned as 1970-01-01 (placeholder; “2021” in EntryTitle)

Spatial Coverage (metadata text): worldwide

ProcessingLevelId: null

Missing/ambiguous metadata: temporal fields inconsistent with year described in EntryTitle

10) ESA WorldCereal products for active cropland per agro-ecological zone - V1
Short Name: urn:eop:VITO

CMR Concept ID: C2734302030-FEDEO

Variables (verbatim): “binary maps… showing where active cropland has been detected… for all growing seasons…”

Temporal Coverage (metadata): time_start returned as 1970-01-01; time_end not returned

Spatial Coverage (metadata text): “per agro-ecological zone” (global vs regional coverage not explicitly stated in returned metadata)

ProcessingLevelId: null

Missing/ambiguous metadata: spatial resolution and the actual year range are not stated in the returned metadata fields

4. Search Reproducibility Log
CMR endpoints used (via MCP server)
search_collections

get_collection_metadata

Query parameters used (as executed)
search_collections

keyword=Sentinel-2 surface reflectance 10 m, instrument=MSI,

temporal=2018-01-01T00:00:00Z,2025-12-31T23:59:59Z,

bounding_box=92,9,101,29,

page_size=50, page_num=1
Result: 0 hits

search_collections

keyword=Sentinel-2, platform=Sentinel-2,

temporal=2018-01-01T00:00:00Z,2025-12-31T23:59:59Z,

page_size=50, page_num=1
Result: 0 hits

search_collections

keyword=Sentinel-2A MSI,

temporal=2018-01-01T00:00:00Z,2025-12-31T23:59:59Z,

page_size=50, page_num=1
Result: 69 hits (first page reviewed; contained FEDEO 10 m maps and TerraScope S2 products, plus HLS 30 m)

search_collections

keyword=ESA WorldCover 10m 2022, provider=FEDEO, page_size=50, page_num=1
Result: 0 hits

get_collection_metadata for concept_ids:

C2207478568-FEDEO, C2207478523-FEDEO,

C2655129129-FEDEO, C2655129178-FEDEO,

C2770608964-FEDEO, C2655128870-FEDEO,

C2734302030-FEDEO,

(plus previously retrieved ASF Sentinel-1 concept metadata in earlier steps)

Candidate GCMD mappings (not validated via GCMD KMS tool in this run)
Croplands / land cover: LAND SURFACE > LAND USE/LAND COVER

Optical reflectance: LAND SURFACE > REFLECTANCE

NDVI / vegetation index: LAND SURFACE > VEGETATION > VEGETATION INDEX

SAR: SPECTRAL/ENGINEERING > RADAR

Paging behavior
Only first page inspected for the 69-hit “Sentinel-2A MSI” keyword search (page_num=1, page_size=50).

Ranking logic (metadata-only)
Collections spanning 2018–2025 and described as high-resolution (even if not explicitly “10 m”) ranked above single-year 10 m maps.

Explicit 10 m land cover / NDVI composites ranked next (but these are year-specific per titles).

Sentinel-2 tile products ending 2021 ranked lower for the 2018–2025 requirement.

UTC timestamps
Run timestamp: 2026-03-14T00:00:00Z

5. Fact-Check / User Verification List
Please verify manually in documentation/collection landing pages before use:

For Sentinel-1 GRD (ASF): confirm pixel spacing / ground resolution for the specific GRD mode(s) you will use over Myanmar; “10 m” is not explicitly stated in the returned collection metadata snippet.

For TerraScope Sentinel-2 (FEDEO): confirm geographic coverage includes Myanmar and confirm which bands are at 10 m and whether products are global or Europe-focused (not explicit in returned metadata).

For WorldCover 2020/2021 (FEDEO): confirm cropland-related class codes and note the CMR temporal fields show 1970 placeholder despite year being in the title.

For WorldCereal active cropland (FEDEO): confirm actual year range, spatial resolution, and whether products cover Myanmar; CMR temporal/resolution fields are incomplete in returned metadata.

Earthdata Search handoff links (collection discovery):

https://search.earthdata.nasa.gov/search?q=SENTINEL-1A_DP_GRD_HIGH

https://search.earthdata.nasa.gov/search?q=SENTINEL-1B_DP_GRD_HIGH

https://search.earthdata.nasa.gov/search?q=SENTINEL-1C_DP_GRD_HIGH

https://search.earthdata.nasa.gov/search?q=ESA%20WorldCover%2010%20meter%20Land%20Cover%20Map%202020

https://search.earthdata.nasa.gov/search?q=ESA%20WorldCover%2010%20meter%20Land%20Cover%20Map%202021

https://search.earthdata.nasa.gov/search?q=TERRASCOPE_S2_L1C

https://search.earthdata.nasa.gov/search?q=TERRASCOPE_S2_TOC

https://search.earthdata.nasa.gov/search?q=ESA_WORLDCEREAL_ACTIVECROPLAND

The assistant said:
Output Agent
{"dataset_concept_ids":["C1214470533-ASF","C3486566209-ASF","C1327985645-ASF","C2207478523-FEDEO","C2207478568-FEDEO","C2655129129-FEDEO","C2655129178-FEDEO","C2770608964-FEDEO","C2655128870-FEDEO","C2734302030-FEDEO"]}
