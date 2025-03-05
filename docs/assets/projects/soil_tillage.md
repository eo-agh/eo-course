# 🌾 **Monitoring Soil Tillage Using Satellite Data**  

## 📌 **Basic Info**  
Detecting **soil tillage activities** is crucial for effective agricultural land management. Monitoring these activities helps in:  
- ✅ **Assessing field maintenance** and soil preparation for cultivation.  
- ✅ **Ensuring compliance with environmental regulations**, especially regarding subsidy programs.  
- ✅ **Tracking soil condition and erosion risks** resulting from tillage practices.  

Satellite-based observation provides an efficient way to identify **when and where soil tillage occurs**. While direct observation of tillage is challenging, its effects on the land surface can be **detected through spectral and radar signal changes**. By analyzing **Sentinel-2 optical data** and **Sentinel-1 SAR backscatter**, we can infer tillage events based on changes in vegetation cover and surface roughness.  

---

## 📊 **Further Info**  
Tillage significantly alters the land surface, leading to:  
✔️ **Increase in bare-soil probability** due to reduced vegetation cover.  
✔️ **Decrease in NDVI (Normalized Difference Vegetation Index)**, indicating soil exposure.  
✔️ **Changes in SAR backscatter**, revealing surface roughness variations.  

The combination of **bare-soil probability increase** and **NDVI decline** provides an effective method for detecting tillage events.  
📌 **Key methodology:**  
- **Start of tillage** is marked by a **sudden rise in bare-soil probability**.  
- **End of tillage** is defined by the **stabilization of this probability**.  
- **Inverse correlation** exists between bare-soil probability and NDVI—when bare soil increases, NDVI decreases.  

🛰️ **Example Case:**  
A cornfield vegetated until **late September**, then tilled in **early October**, would exhibit:  
✅ A **sharp increase in bare-soil probability**, confirming tillage activity.  
✅ A **notable drop in NDVI**, signaling loss of vegetation cover.  
✅ A **SAR signal change in Sentinel-1**, indicating surface roughness modifications.  

---

## 📌 **Marker Output**  
This analysis provides:  
📍 **Detected tillage events** – specific dates when soil was tilled.  
📍 **Bare-soil probability values** for each detected event.  
📍 **NDVI trend analysis** confirming vegetation loss.  

### 🔧 **User-Controlled Parameters**  
Users can adjust the model sensitivity to reduce false positives and false negatives by modifying:  
- **Threshold for bare-soil probability increase** to validate tillage detection.  
- **Minimum NDVI drop required** for a confirmed event.  
- **Temporal smoothing filters** to reduce noise in data.  

---

## 📡 **Data Sources & Methods**  
This project utilizes a combination of **optical, radar, and environmental datasets**:  
- 🛰️ **Sentinel-2 MSI** – NDVI and spectral reflectance analysis.  
- 📡 **Sentinel-1 SAR** – Backscatter changes indicating surface disturbance.  
- 🌍 **Copernicus Land Monitoring Services** – Reference land cover classification.  
- 📏 **In situ data collection** – Ground truth measurements using **field spectroradiometers** or farmer reports.  

📌 **Final Deliverables:**  
- Interactive maps displaying **historical and current tillage patterns**.  
- Automated script for **tillage event detection** using satellite data.  
- Analytical report correlating **tillage trends with land management practices**.  

---

🚀 **This project contributes to precision agriculture by providing reliable insights into soil tillage and land preparation activities.**  
📅 **Expected completion: Summer 2025.**  


📌 **[Back to Projects](../projects.md)**  
