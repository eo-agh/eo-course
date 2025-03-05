# 🌍 **Monitoring Bare-Soil Exposure Using Satellite Data**  

## 📌 **Basic Info**  
The **bare-soil marker** is used to detect areas with **exposed bare soil**, which can result from:  
- **Recent plowing** or tillage activities.  
- **Harvesting**, leaving non-photosynthetic vegetation residues.  
- **Natural vegetation drying**, revealing soil due to seasonal or climatic conditions.  

While **plowing or harvesting events** themselves cannot be directly observed in satellite imagery, their **effects are detectable**. By analyzing **Sentinel-2 optical data**, we can classify areas with bare soil based on **spectral characteristics**.  

📌 **Key Observations:**  
- **Bare soil** appears **brownish or grayish** in **false-color Sentinel-2 images**.  
- **Vegetation presence** is indicated by **red tones** in false-color imagery.  
- The **bare-soil marker** assigns a **probability score (0 to 1)** for each Sentinel-2 observation.  
- Observations with **probability above a defined threshold (e.g., 0.8)** are classified as **bare-soil events**.  

---

## 📊 **Further Info**  
The **timing of bare-soil exposure** depends on:  
- 🌾 **Crop type** being cultivated.  
- 🚜 **Farming practices** such as tillage and harvesting schedules.  

By analyzing **temporal distributions of detected bare-soil observations**, we can distinguish **different land-use patterns**.  

🛰️ **Example Case:**  
- **Cornfields** in Slovenia exhibit **bare soil from early January to June** and **again after mid-October**.  
- **Summer barley fields** show **exposed bare soil earlier in the year compared to winter barley** due to different sowing periods.  
- **Vegetable fields** display **bare-soil detections throughout the year**, reflecting multiple sowing and harvesting cycles.  
- **Permanent meadows** are expected to remain **vegetated year-round**, meaning any bare-soil detection could indicate **land-use inconsistencies**.  

📌 **Visualization:**  
- 📊 **Time-series analysis** of NDVI (green) vs. bare-soil probability (orange).  
- 🖼️ **Sentinel-2 false-color images** showing **bare-soil classification** over time.  
- 🔍 **Bare-soil masks** overlaid on **true-color Sentinel-2 images** to confirm detections.  

---

## 📌 **Marker Output**  
This analysis generates:  
📍 **Detected bare-soil events**, marking periods of exposed soil.  
📍 **Probability values** for each observation.  
📍 **Temporal distribution plots** to assess land-use patterns.  

### 🔧 **User-Controlled Parameters**  
To fine-tune detection accuracy, users can modify:  
- **Threshold probability for bare-soil classification** (e.g., 0.8).  
- **Smoothing filters** to minimize noise in spectral changes.  
- **Time-window constraints** to detect seasonal land-use trends.  

---

## 📡 **Data Sources & Methods**  
This project integrates **optical and environmental data sources**:  
- 🛰️ **Sentinel-2 MSI** – Multispectral analysis for vegetation indices and soil exposure detection.  
- 🌍 **Copernicus Land Monitoring Services** – Baseline land cover classification.  
- 📏 **In situ measurements** – Spectroradiometer data for validation and calibration.  

📌 **Final Deliverables:**  
- 📊 **Maps showing temporal changes in bare-soil exposure**.  
- 📈 **Automated processing script for Sentinel-2-based detection**.  
- 📖 **Report analyzing trends across different crop types and farming systems**.  

---

🚀 **This project enhances agricultural monitoring by providing insights into soil exposure, land-use patterns, and farming activity trends.**  
📅 **Expected completion: Summer 2025.**  



📌 **[Back to Projects](../projects.md)**  
