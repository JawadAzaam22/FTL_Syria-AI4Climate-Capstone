# Idea Proposal

## 1. Project Idea

### Problem Statement

Syrian farmers face compounding climate-driven risks — drought, water scarcity, erratic rainfall, and heat waves — yet they lack accessible, localized decision-support tools. Existing agricultural information is scattered across weather portals, soil databases, satellite products, and field records, and most available tools present raw data without explaining what it means, why it matters, or what the farmer should do. The result is reactive farming: irrigation is applied too late, crop choices ignore soil–climate fit, and yield losses accumulate silently.

### Specific Goal

Build an AI-powered agricultural decision-support platform designed for the Syrian farmer as the single end-user. The platform integrates four data sources — Sentinel-2 satellite imagery (NDVI/NDMI), ERA5-Land climate reanalysis, SoilGrids soil properties, and optional field sensors (ESP32) — and converts them into four interpretable outputs:

1. **Crop suitability** ("Which crop is better suited for this field, and why?")

2. **Water stress alerts** ("Possible stress detected — reason, confidence, and verification step")

3. **Yield estimation with an uncertainty range** (not a single number)

4. **Irrigation advice** based on FAO-56

Every recommendation carries **cause, data source, confidence level, and limitations** — an explicit "explanation layer" is a core design requirement, not an add-on. The initial scope targets **five governorates** (Al-Hasakah, Aleppo, Hama, As-Suwayda, Tartus), with a national model + local calibration design that allows future expansion across various crops.

## 2. Relevance to Sustainable Development Goals (SDGs)

The platform directly supports four SDGs:

* **SDG 2 — Zero Hunger:** Improves crop selection and early stress detection, protecting crop yields in a country where food security is a national priority.

* **SDG 6 — Clean Water & Sanitation:** Reduces water waste through FAO-56-based irrigation advice and stress-driven scheduling, targeting the agricultural sector that consumes the majority of Syria's water.

* **SDG 13 — Climate Action:** Provides an adaptation tool for climate-vulnerable farmers, converting climate data into actionable, localized recommendations.

* **SDG 1 — No Poverty:** Protects smallholder livelihoods by reducing input waste and crop failure risk — a direct pathway to rural income stability.

Secondary alignment: **SDG 12 (Responsible Consumption)** through resource-use efficiency, and **SDG 17 (Partnerships)** through open-data reliance (Copernicus, FAO).

## 3. Literature Examples

### Example 1 — RaySat (Syrian remote-sensing irrigation platform)

A Syrian platform providing satellite-based irrigation advisory to farmers. Reported outcomes include **37.7% water savings** and **15–20% yield increase**, with adoption by more than **10,000 users**. RaySat demonstrates that the target problem is real, the market exists, and satellite-driven advice is feasible in the Syrian context — while also revealing gaps the proposed platform addresses: limited explanation of recommendations, weak uncertainty communication, and no integrated crop-suitability layer.

### Example 2 — Satellite-based crop water stress classification using Sentinel-2 and machine learning

Peer-reviewed studies (e.g., olive orchards in Spain using XGBoost with NDVI, NDMI, and NDWI indices from Sentinel-2) demonstrate that combining spectral indices with ML classifiers can reliably distinguish water-stress levels. Complementary work shows that gradient-boosting models integrated with FAO-56 achieve up to **91% accuracy** in irrigation scheduling, and that XGBoost can predict soil moisture depletion with $R^2 \ge 0.72$. These results validate the technical approach — Sentinel-2 indices + FAO-56 + ML — as a scientifically grounded basis for stress detection and irrigation advice.