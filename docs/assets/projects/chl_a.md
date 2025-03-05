# 🌊 **Monitoring Chlorophyll Levels in Solina Reservoir Using Satellite Data**  

## 📌 **Basic Info**  
Monitoring **chlorophyll concentrations** in inland water bodies is essential for understanding **water quality, algal blooms, and ecological changes**. This project focuses on using **multi-source satellite data and in situ measurements** to track chlorophyll-a levels in the **Solina Reservoir**, one of Poland’s largest artificial lakes.  

The project integrates:  
- **Sentinel-3 OLCI** (Ocean and Land Colour Instrument) – Daily revisit time, enabling continuous monitoring.  
- **Sentinel-2 MSI** (Multispectral Instrument) – Higher spatial resolution (5-day revisit time), complementing Sentinel-3 observations.  
- **In situ measurements** – Collected using **field spectroradiometers and water sampling** for validation and model calibration.  

---

## 📊 **Further Info**  
Chlorophyll-a is a **key indicator of phytoplankton biomass** and can be used to detect **eutrophication levels** in freshwater reservoirs.  
By combining **high-temporal-resolution Sentinel-3 data** with **high-spatial-resolution Sentinel-2 imagery**, we can:  
✔️ Improve the **accuracy of chlorophyll-a concentration estimates**.  
✔️ Analyze **seasonal and spatial variations** of water quality in Solina.  
✔️ Detect **algal bloom events** and their progression over time.  

📌 **Key Methodology:**  
1. **Preprocessing Sentinel-3 OLCI data** – Chlorophyll index retrieval using band ratios and bio-optical models.  
2. **Integration with Sentinel-2 MSI** – Higher spatial resolution data to refine Sentinel-3 results.  
3. **Validation with in situ data** – Using field spectroradiometer readings and laboratory analysis of water samples.  
4. **Time-series analysis** – Detecting chlorophyll trends over different seasons.  

🛰️ **Example Case:**  
- High chlorophyll-a levels in **summer months** due to increased nutrient load and higher temperatures.  
- Lower concentrations in **winter**, with stable water conditions.  
- Sentinel-3 provides **daily variability**, while Sentinel-2 enhances **detailed spatial analysis**.  

---

## 📌 **Project Output**  
This study will produce:  
📍 **Chlorophyll concentration maps** for Solina Reservoir.  
📍 **Time-series analysis** showing chlorophyll trends over time.  
📍 **Comparison between Sentinel-3, Sentinel-2, and in situ measurements** for accuracy assessment.  

### 🔧 **User-Controlled Parameters**  
Users can fine-tune:  
- **Thresholds for chlorophyll detection** (e.g., eutrophication alert levels).  
- **Integration models** between Sentinel-2 and Sentinel-3 data.  
- **Temporal aggregation** to minimize noise in satellite-derived results.  

---

## 📡 **Data Sources & Methods**  
This project combines **remote sensing and field measurements**:  
- 🛰️ **Sentinel-3 OLCI** – Daily revisit time, ocean color-based chlorophyll detection.  
- 🛰️ **Sentinel-2 MSI** – 5-day revisit time, high-resolution water quality monitoring.  
- 🌍 **Copernicus Water Quality Services** – Reference chlorophyll datasets.  
- 📏 **In situ spectroradiometer measurements** – Ground truth validation.  

📌 **Final Deliverables:**  
- **Chlorophyll concentration maps and trends**.  
- **Automated processing script for Sentinel-based monitoring**.  
- **Report on water quality changes and potential eutrophication risks**.  

🚀 **This project will contribute to sustainable water resource management by providing an advanced monitoring system for chlorophyll levels in Solina Reservoir.**  
📅 **Expected completion: Summer 2025.**  

📌 **[Back to Projects](../projects.md)**  
