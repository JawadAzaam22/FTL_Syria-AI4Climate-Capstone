# Arki Pilot — Idea Proposal - V2

## 1. Project Idea

**Project title and climate challenge:**  
**Arki Pilot: An AI-Powered Agricultural Decision-Support Platform for Syrian Farmers.** The project addresses drought, water scarcity, irregular rainfall, and heat waves, which make crop selection and water management increasingly difficult in Syria.

**Problem statement:**  
Syrian farmers often lack accessible, field-specific guidance. Relevant information is scattered across satellite imagery, weather services, soil databases, and field measurements. These sources are difficult to combine and interpret, leaving farmers without clear support when choosing crops, identifying possible water stress, estimating yields, or planning irrigation.

**Main research question:**  
How can satellite, climate, soil, and optional field-sensor data be combined with agricultural rules and selected machine-learning methods to provide explainable crop and water-management guidance for Syrian farmers?

**Datasets and sources:**  
- **Sentinel-2:** Satellite imagery and vegetation indicators such as NDVI and NDMI.
- **ERA5-Land:** Climate information, including rainfall and temperature.
- **SoilGrids:** Estimated soil properties relevant to crop suitability.
- **Optional field sensors (e.g. ESP32):** Local measurements such as soil moisture and temperature, used for verification and calibration when available.

**Proposed AI/ML approach and expected output:**  
Arki Pilot will use a hybrid approach combining explainable agricultural rules with selected machine-learning methods. It will assess crop suitability using crop requirements and limiting field conditions; analyze satellite time series to monitor crop development and possible water stress; and use historical and environmental data for yield estimation when sufficient data are available. Irrigation guidance will be based on the FAO-56 water-requirement approach, with local measurements used where available. The prototype will provide four outputs: **crop-suitability assessment, possible water-stress alerts, yield estimates with an uncertainty range, and irrigation guidance**. Each result will show its main reason and relevant data limitations. Recommendations support the farmer; they do not replace the farmer’s decision.

## 2. Relevance to Sustainable Development Goals (SDGs)

- **SDG 2 — Zero Hunger:** Supports crop decisions and early identification of possible crop stress.
- **SDG 6 — Clean Water and Sanitation:** Promotes more informed and efficient agricultural water use.
- **SDG 13 — Climate Action:** Helps farmers adapt agricultural decisions to climate-related risks.
- **SDG 1 — No Poverty:** Supports smallholder livelihoods by helping reduce avoidable crop and resource losses.

## 3. Literature Examples

1. **RaySat — Syrian satellite-based irrigation advisory platform:** A relevant local example of using satellite information to support irrigation decisions. The project proposal reports water savings and yield improvements, demonstrating the relevance of digital agricultural advice in the Syrian context.

2. **Satellite-based crop water-stress research using Sentinel-2 and machine learning:** Research on crop monitoring, including olive orchards, has used vegetation and moisture indices such as NDVI and NDMI with machine-learning methods to identify water-stress conditions. This provides a relevant research basis for Arki Pilot’s satellite-monitoring component.
