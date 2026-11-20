# AgriPilot — Literature Review, Data Research and Technology Review

**Project:** AgriPilot (Arki Pilot) — Agricultural Decision-Support Platform for Syrian Farmers  
**Submission date:** 20 November 2026  


## Project Scope

AgriPilot is designed to support Syrian farmers with crop and irrigation planning. The core project focuses on wheat, barley, maize and cotton in Hasakah, Aleppo, Hama, As-Suwayda and Tartus.

The project is organized into two phases:

- **Phase 1 — Core season-ahead planning:** uses field information, soil information and historical climate data to generate crop-suitability comparisons, indicative yield estimates, growth-stage stress assessments and irrigation advice under dry, average and wet scenarios.
- **Phase 2 — Optional in-season monitoring:** investigates the use of satellite information, including Sentinel-2 vegetation indices, and other updated observations to support monitoring during the growing season.

The information selected for the core data layer is sufficient to support the planned Phase 1 prototype. Work on identifying and accessing suitable satellite information will continue as part of the optional Phase 2.

---

# Part 1 — Literature Review

## 1. Introduction

Agricultural planning depends on climate, soil, crop requirements and water availability. These factors are particularly important in Syria, where farmers face irregular rainfall, drought and water scarcity. Reviewing existing agricultural research and methods helps identify suitable approaches for crop suitability, yield estimation, stress assessment and irrigation planning.

## 2. Thematic Review

### 2.1 Crop water requirements and irrigation

FAO Irrigation and Drainage Paper 56 (Allen et al., 1998) presents the reference evapotranspiration and crop-coefficient approach for estimating crop water requirements. It provides a practical and interpretable basis for irrigation scheduling. FAO Paper 33 (Doorenbos & Kassam, 1979) explains how water deficit can affect crop yield through the yield-response factor. These methods are relevant to AgriPilot because they provide agronomic foundations for its water-balance, irrigation and yield-related calculations.

### 2.2 Climate and soil information

ERA5-Land provides historical climate information that can be used to examine past seasonal conditions and construct climate analogues. SoilGrids provides spatial soil-property information that can contribute to an initial field profile. Together, these sources provide the climate and soil context needed for the core season-ahead planning functions.

### 2.3 Satellite information and crop monitoring

Sentinel-2 provides multispectral satellite observations from which vegetation indicators such as NDVI and NDMI can be derived. These indicators are useful for observing crop development during an actual growing season. For AgriPilot, satellite information is considered part of the optional Phase 2 monitoring layer rather than a requirement for the core season-ahead plan.

### 2.4 Machine learning in agricultural analysis

Machine-learning methods such as Random Forest and Gradient Boosting can model relationships between climate, soil and crop characteristics. They can support yield estimation and pattern analysis. AgriPilot combines data-driven methods with agronomic calculations so that the outputs remain linked to understandable agricultural factors.

## 3. Literature Review Conclusion

The reviewed literature supports the combination of historical climate information, soil properties and established crop-water methods for agricultural planning. FAO-56 and FAO-33 provide the agronomic basis for water and yield-response calculations, while machine learning can support the analysis of crop and climate relationships. Satellite observations can extend the system with in-season monitoring in Phase 2. AgriPilot brings these approaches together in a single planning workflow for its selected crops and Syrian governorates.

---

# Part 2 — Data Research

## 1. Introduction

The purpose of the data research is to identify the information needed to support AgriPilot's agricultural planning functions. The core data layer combines climate and soil information with field and crop details. These inputs are used to compare climate scenarios, assess crop suitability, estimate yield and prepare irrigation advice.

## 2. Data Sources

| Data source | Information used | Role in AgriPilot |
|---|---|---|
| **ERA5-Land** | Historical climate variables, including temperature and precipitation | Provides historical climate information for the Phase 1 climate-analogue scenarios. |
| **SoilGrids** | Spatial soil properties, including soil texture and related characteristics | Supports the initial soil profile used in crop and water-balance analysis. |
| **Field information** | Field location, selected crop and planting date | Defines the location and period for the season-ahead plan. |
| **Sentinel-2 (optional)** | Multispectral satellite observations used to derive NDVI and NDMI | Supports possible Phase 2 crop monitoring during the growing season. |
| **Updated observations (optional)** | Updated weather and field observations | May support Phase 2 monitoring and interpretation. |

## 3. Data Selection and Relevance

ERA5-Land was selected because historical climate information is important for comparing past seasonal conditions and generating climate-analogue scenarios. SoilGrids was selected to provide spatial soil information that can support the field profile and crop analysis. Field location, crop and planting date connect these datasets to the farmer's planning question. Sentinel-2 is relevant to observing vegetation during the growing season and is therefore included as an optional source for Phase 2.

## 4. Data Preparation and Analysis

The core workflow organizes climate information by the agricultural season and prepares the soil and field inputs for the selected location. The planner compares historical analogue seasons and selects dry, average and wet scenarios using seasonal rainfall percentiles. These scenarios are then used by the crop-suitability, yield-estimation, stress-assessment and irrigation modules.

For the optional Phase 2, satellite observations can be processed into vegetation indicators such as NDVI and NDMI. Their time series may then be used to observe changes in crop development during the season.

## 5. Data Research Conclusion

The selected climate and soil information provides the required foundation for the core Phase 1 planning functions. The data layer supports the planned crop comparison, scenario-based yield estimation, stress assessment and irrigation advice. Further work will focus on identifying suitable satellite information and access methods for the optional Phase 2 monitoring layer.

---

# Part 3 — Technology Review

## 1. Introduction

The technology review considers the tools needed to prepare agricultural data, perform crop and water calculations, develop the planning services and present results to users. The selected technologies support the core season-ahead workflow while allowing optional monitoring functions to be added later.

## 2. Technology Overview and Relevance

| Technology | Purpose | Relevance to AgriPilot |
|---|---|---|
| **Python** | Main programming language | Supports data processing, agricultural calculations and machine learning. |
| **pandas and NumPy** | Data handling and numerical processing | Prepare climate, soil and crop inputs and perform calculations. |
| **xarray and geospatial libraries** | Work with gridded climate and spatial data | Support climate and location-based data processing. |
| **FastAPI** | Backend application framework | Provides services and endpoints for the planning functions. |
| **Streamlit** | User-interface framework | Presents the planning workflow and results to users. |
| **FAO-56 calculations** | Crop-water balance and irrigation scheduling | Provides the agronomic basis for irrigation advice. |
| **scikit-learn / Gradient Boosting** | Machine-learning methods | Supports analysis and indicative yield estimation. |
| **SQLite** | Database | Stores prototype application information. |
| **Sentinel-2 data tools (optional)** | Satellite data processing | May support the Phase 2 monitoring layer. |

## 3. Comparison and Evaluation

Python-based tools provide a unified environment for data processing, model development and application integration. FastAPI is suitable for organizing backend services, while Streamlit supports rapid development of a user-facing prototype. pandas, NumPy and xarray provide tools for structured and gridded data processing. FAO-56 offers an established agronomic method for irrigation planning, while machine-learning methods can support analysis of non-linear relationships in agricultural data.

For the core project, these tools provide a practical balance between functionality and implementation time. Satellite data processing is treated separately because it belongs to the optional in-season monitoring phase.

## 4. Use Cases and Examples

FAO-56 is widely used as a basis for estimating crop water requirements and irrigation scheduling. ERA5-Land and SoilGrids provide climate and soil information for environmental and agricultural analysis. Sentinel-2 is used in vegetation monitoring through multispectral imagery and derived indices. These examples show how the selected methods and data types can contribute to the different functions planned for AgriPilot.

## 5. Gaps and Further Work

The main technology focus for Phase 1 is to integrate the climate and soil inputs with the crop-suitability, yield, stress and irrigation functions. For Phase 2, further work is needed to identify appropriate satellite data sources, access methods and processing steps for monitoring during the growing season. This optional work will be developed without changing the role of Phase 1 as the core planning system.

## 6. Technology Review Conclusion

The selected technology stack supports the main AgriPilot workflow: preparing climate and soil information, performing agronomic and machine-learning calculations, connecting the backend services and presenting results through the interface. The core technologies are appropriate for the season-ahead planning phase. Satellite data tools remain an optional extension for in-season monitoring.

---

# References

1. Allen, R. G., Pereira, L. S., Raes, D., & Smith, M. (1998). *Crop Evapotranspiration: Guidelines for Computing Crop Water Requirements.* FAO Irrigation and Drainage Paper 56.
2. Doorenbos, J., & Kassam, A. H. (1979). *Yield Response to Water.* FAO Irrigation and Drainage Paper 33.
3. Muñoz-Sabater, J., et al. (2021). ERA5-Land: A state-of-the-art global reanalysis dataset for land applications. *Earth System Science Data, 13*, 4349–4383.
4. Poggio, L., et al. (2021). SoilGrids 2.0: Producing soil information for the globe with quantified spatial uncertainty. *SOIL, 7*, 217–240.
5. Drusch, M., et al. (2012). Sentinel-2: ESA's optical high-resolution mission for GMES operational services. *Remote Sensing of Environment, 120*, 25–36.
6. Breiman, L. (2001). Random forests. *Machine Learning, 45*, 5–32.
