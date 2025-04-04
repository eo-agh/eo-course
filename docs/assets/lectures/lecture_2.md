# 🛰️ Lecture 2: Remote Sensing Analysis & Applications  

---

## 🎯 Learning Objectives  

By the end of this lecture, you will understand:

- **How to create satellite imagery**, by mapping quantative sensor data to a range of colors for qualitative visual analysis.
- **What are spectral indices**, including NDVI and other vegetation indices, and their importance in environmental monitoring.
- **Principles and methods of image classification**, including supervised and unsupervised approaches.
- **How to preprocess remote sensing data**, including atmospheric and geometric corrections.
- **Common applications of remote sensing across various sectors** (e.g., agriculture, urban mapping, disaster management).
- **Validation and accuracy assessment of remote sensing analysis**.

---

## 📌 Lecture Topics Overview  

1. **Band compositions**
2. **Spectral Indices**  
3. **Image Classification Techniques**  
4. **Applications of Remote Sensing**  
5. **Accuracy Assessment and Validation**  


## 1. Creating Satellite Imagery

When we combine data collected by remote sensors with our knowledge of the observed target’s spectral signatures, we can learn about many geophysical parameters, which are the properties and characteristics of different parts of the Earth system. In this lesson, you’ll learn about using satellite imagery to visualize this information, and about how data products at different processing levels allow you to analyze it quantitatively. You will also explore case studies where these techniques are applied to address real-world problems. You will then be able to answer the question, HOW CAN I USE REMOTE SENSING DATA?

Example (below): This Advanced Spaceborne Thermal Emission and Reflection Radiometer (ASTER) image from August 14, 2002, combines visible and infrared bands to show the Biscuit Fire in the Northwest U.S., with active fire areas in red coloring. Credit: NASA/METI/AIST/Japan Space Systems, and U.S./Japan ASTER Science Team

![Remote Sensing Example 1](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image1.jpg)  

**The remotely sensed data from satellite sensors is typically visualized with satellite imagery.** This imagery can represent one channel or a combination of several channels from the sensor. While the satellite sensor data itself is **quantitative**, the imagery is created by mapping this data to a range of colors for **qualitative visual analysis**.

![Remote Sensing Example 2](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image2.jpg)  

## 1.1 Single Channel Imagery

For each single band, satellite remote sensors directly measure radiance, which is the intensity of radiation in a given direction. Radiance is often quantified using a Brightness Temperature scale, expressed in degrees Celsius. The GOES "Clean Infrared" channel (or Band 13) is shown here as an example, and a color bar is applied to the data in order to highlight the cloud top surfaces with the lowest thermal temperatures. The red to magenta color range corresponds to the coldest cloud tops and strongest convection. Note also the warm cloud, land, and water surfaces that are less prominent in the light gray shades, and a different color curve could be used instead to highlight these warm features in this same scene. This single band can be used for analysis on its own, or combined with other bands in more complex imagery.

![Remote Sensing Example 3](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image3.png)  

"Clean Infrared" Band 13 from GOES Advanced Baseline Imager (ABI) centered over Colombia South America for 17 July 2024 at 1800 UTC. A color curve is applied to the Brightness Temperature data where warm features are in light gray shades and cold features are in red to black to gray to magenta shades. Source: NASA Worldview

Given measurements of radiance, the ratio of the radiation striking a surface to the radiation reflected off can then be calculated, and this is referred to as reflectance. The same scene from GOES ABI is shown here but for the "Red Visible" Band 2 as single channel imagery. The reflectance is displayed on a black to white scale with the highest values in white to correspond with cloud features. Note how the cold clouds are less obvious compared to the prior Clean Infrared imagery, but the presence of all clouds is much easier to analyze, particularly over the water/ocean area on the left side of the imagery. One way that scientists create more complex satellite imagery is to combine reflectances from multiple bands.

![Remote Sensing Example 4](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image4.jpg)  
"Red Visible" Band 2 from GOES Advanced Baseline Imager (ABI) centered over Colombia South America for 17 July 2024 at 1800 UTC (same as above image of "Clean Infrared"). A black to white scale is applied with the largest reflectance values in white. Source: NASA Worldview

## 1.2 True Color Imagery

🎯 **True Color** imagery was designed to display the Earth in colors similar to what we might see with our own eyes. The product is primarily a combination of available channels that are sensitive to the red, green, and blue visible light. The image below shows how the VIIRS instrument's visible red, green and blue bands are combined to generate the composite true color image (i.e., a Red-Green-Blue, or RGB imagery product).

In the graphic below, the VIIRS images from each channel (red, green, and blue) show reflectances from these bands in a black to white scale. Each single channel image looks similar, but they have important differences. For example, in the red image, the water is darker, and the scene is slightly dimmer. The blue is lighter because it's shorter wavelengths are more easily scattered by the atmosphere. The values that represent the cloudy areas are very similar because reflectance by clouds doesn’t depend very much on wavelength. However you can see the red and green bands are more absorbed (i.e., appear darker) by the water than the blue band. When the three visible channels are combined (i.e., an RGB product), you can now make out bare soil and brown colors. The water looks bluer, and the clouds still appear white.

![Remote Sensing Example 5](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image5.jpg)  
S-NPP VIIRS instrument combination of visible wavelengths resulting in a True Color image as your eye would see from space. Source: NASA

## 1.3 False Color Imagery

While true color images are created by assigning the red, green, and blue colors to the red, green, and blue visible wavelengths, respectively, false color images are created by assigning different wavelengths to one or more colors. For example, we can use color to depict non-visible wavelengths, such as infrared or ultraviolet which may be associated with things like atmospheric gases and heat, to create an enhanced image for analysis. This is why the image colors may not correspond to what we expect to see.

![Remote Sensing Example 6](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image6.jpg)  
Landsat Imagery Comparison of a Wildfire Scene: True Color RGB (left), False Color RGB (right). Source: NASA

The image on the left is the visible true color image of a wildfire. Smoke is obscuring the burned area. RGB Imagery Color Components to Wavelengths: Red = 0.66 µm, Green = 0.55 µm, Blue = 0.47 µm.

To "see through” the smoke, we can use the shortwave infrared (SWIR) and near-infrared (NIR) channels. In the false color image on the right for the same fire event, the areas in purple coloring stands out and represents land that has been burned. Even though we can see through the smoke, you can still see shades of smoke in the right image as dark smudges. Image Color to Wavelength: Red = 1.6 µm (Shortwave Infrared), Green = 1.2 µm (Near-Infrared), Blue = 2.1 µm (Shortwave Infrared).

Alternatively, when using an RGB imagery product, each pixel contains a red, green, and blue color component toward the final pixel color. A satellite band or band difference is used within each color component of the RGB in order to identify multiple geophysical parameters within one image (i.e., cloud thickness, phase, and height all within the same image).

![Remote Sensing Example 7](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image7.png)  
Source: Himawari-8 AHI

Then, the geophysical parameter range is scaled between black (i.e., no color) to the maximum color intensity per RGB component (i.e., full red, full green, or full blue).

![Remote Sensing Example 8](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image8.png)  
Source: Himawari-8 AHI

## 2. Spectral Indices

📌 **What is a spectral index?**

- A mathematical equation that is applied on the various spectral bands of an image per pixel
- Simple band ratios that highlight a specific process or property on the land surface
- Reduce effects of atmosphere, instrument noise, sun angle: allows for consistent spatial and temporal comparisons

🎯 Spectral indices are used to enhance particular land surface features or properties, e.g. vegetation, soil, water. There are developed based on the spectral properties of the object of interest.

**Applications of Spectral Indices include, e.g.:**

- Vegetation Health
- Burned Area Mapping and Fire Severity
- Water Content
- Biophysical Parameters (i.e., biomass)
- Geologic Mapping 

![Spectral Indice Example 1](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image11.png)  

By examining the spectral curves of various objects, one can detect unique variations in their behavior. For instance, a noticeable dip in the reflectance curve might signal the presence of a specific type of vegetation. These distinct features on the **spectral profiles** allow researchers to develop **indices** that are commonly employed for image interpretation.

![Spectral Indice Example 2](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image12.png)  
Source: Ma, M., et al. (2007) Change in area of Ebinur Lake during the 1998–2005 period. International Journal of Remote Sensing, 28(24), 5523-5533.

## 2.1 Deep dive into Spectral Indices

In the following material, the Spectral Indice's formula use letter symbols to represent the reflectance values in specific spectral channels - for example, R represents the reflectance in the red channel, while NIR denotes that in the near-infrared channel, among others. These equations are general and not tied to images from any particular satellite. To calculate any given coefficient in practice, one must substitute the appropriate channel that covers the required wavelength range for the specific satellite being used. Typically, these formulas are simple algebraic expressions that have been refined over years of scientific research to highlight certain land cover types, such as vegetation, and to assess its condition.

Beyond their basic function, these indices - particularly the Vegetation Index (VI) and the Normalized Difference Vegetation Index (NDVI) - have become indispensable tools in the study of vegetation health. Modern remote sensing technologies have significantly improved the accuracy of reflectance measurements across various spectral bands. This progress has not only deepened our understanding of ecosystem dynamics but has also expanded the applications of these indices into fields like precision agriculture, environmental monitoring, and even urban planning. Researchers continue to innovate, adapting these traditional metrics to new satellite platforms and emerging challenges in environmental management.

## 2.1.1 What is NDVI?

📌 **Normalized Difference Vegetation Index**

– Based on the relationship between red and near-infrared wavelengths
– Chlorophyll strongly absorbs visible (red)
– Plant structure strongly reflects near-infrared

![Spectral Indice Example 3](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image13.png)  

**NDVI Formula:**

$$
NDVI = \frac{NIR - R}{NIR + R}
$$

Where: 
- NIR means Near-Infrared
- R - Red
  
**Values range from -1.0 to 1.0.**
– Negative values to 0 mean no green leaves.
– Values close to 1 indicate the highest possible density of green leaves.

![Spectral Indice Example 4](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image14.png)

Source credit: Robert Simmon

**NDVI and seasonality**

Remote sensing is used to track the seasonal changes in vegetation. Monthly NDVI images from MODIS or Landsat can be used to monitor phenology.

![Spectral Indice Example 5](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image15.png)

NDVI Images of North America in Winter and Summer. Credit: spacegrant.montana.edu

**How can we detect anomalies using NDVI?**

1. Departure of NDVI from the long-term average, normalized by long-term variability
2. Generated by subtracting the long-term mean from the current value for that month of the year for each grid cell
3. Indicates if vegetation greenness at a particular location is typical for that period or if the vegetation is more or less green
   
![Spectral Indice Example 6](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image16.png)
NDVI Anomalies in the Southwestern United States

**NDVI Example Calculation**

![Spectral Indice Example 7](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image17.png)
NDVI Anomalies in the Southwestern United States

![Spectral Indice Example 8](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image18.png)
NDVI Anomalies in the Southwestern United States

![Spectral Indice Example 9](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image19.png)
NDVI Anomalies in the Southwestern United States

# Remote Sensing Indices and Formulas

### 2. **NDTI** - Normalized Difference Turbidity Index
**Formula**:
$$
NDTI = \frac{R - G}{R + G}
$$
**Range:** from -1 to +1  
**Description:** Measures water turbidity. Higher positive values indicate higher turbidity (cloudy or sediment-rich water), while lower values suggest clearer water.

![Spectral Indice Example 10](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image20.png)

Lizcano-Sandoval, Luis & Anastasiou, Christopher & Montes, Enrique & Raulerson, Gary & Sherwood, Edward & Muller-Karger, Frank. (2022). Seagrass distribution, areal cover, and changes (1990–2021) in coastal waters off West-Central Florida, USA. Estuarine Coastal and Shelf Science. 279. 108134. 10.1016/j.ecss.2022.108134. 


---

### 3. **NDCI** - Normalized Difference Chlorophyll Index
**Formula**:
$$
NDCI = \frac{R_{708nm} - R_{665nm}}{R_{708nm} + R_{665nm}}
$$
**Range:** from -1 to +1  
**Description:** Detects chlorophyll concentration in aquatic environments. Higher values indicate increased chlorophyll (algal blooms), while low values suggest low algae presence.

<iframe width="560" height="315" src="https://www.youtube.com/watch?v=YKIvNWGZjfQ" title="YouTube video player" frameborder="0" allowfullscreen></iframe>


---

### 4. **FAI** - Floating Algae Index
**Formula**:
$$
FAI = R_{859nm} - \left( R_{645nm} + (R_{1240nm} - R_{645nm}) \times \frac{859 - 645}{1240 - 645} \right)
$$
**Range:** variable (negative or positive)  
**Description:** Highlights floating algae presence. Positive high values indicate floating algae blooms.

![Spectral Indice Example 10](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image21.png)

Zhao, Dan & Li, Junsheng & Hu, Rongming & Shen, Qian & Zhang, Fangfang. (2018). Landsat-satellite-based analysis of spatial–temporal dynamics and drivers of CyanoHABs in the plateau Lake Dianchi. International Journal of Remote Sensing. 39. 1-20. 10.1080/01431161.2018.1488289. 

---

### 5. **AFAI** - Alternate Floating Algae Index
**Formula**:
$$
AFAI = R_{865nm} - \left( R_{665nm} + (R_{1610nm} - R_{665nm}) \times \frac{865 - 665}{1610 - 665} \right)
$$
**Range:** variable (negative or positive)  
**Description:** Similar to FAI, identifies floating algae on water surfaces. Positive values strongly indicate algae presence.

![Spectral Indice Example 11](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image22.png)

Descloitres, Jacques & Minghelli, Audrey & Steinmetz, François & Chevalier, Cristèle & Chami, Malik & Berline, Leo. (2021). Revisited Estimation of Moderate Resolution Sargassum Fractional Coverage Using Decametric Satellite Data (S2-MSI). Remote Sensing. 13. 5106. 10.3390/rs13245106. 

---

### 6. **EVI** - Enhanced Vegetation Index
**Formula**:
$$
EVI = 2.5 \times \frac{NIR - R}{NIR + 6 \times R - 7.5 \times B + 1}
$$
**Range:** typically from -1 to +1  
**Description:** Sensitive to dense vegetation and less affected by atmospheric conditions compared to NDVI. High values reflect dense, healthy vegetation.

![Spectral Indice Example 12](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image23.png)
EVI, Italy. Acquired on 08.10.2017, processed by Sentinel Hub. Source: https://custom-scripts.sentinel-hub.com/custom-scripts/sentinel-2/evi/ 

---

### 7. **SAVI** - Soil-Adjusted Vegetation Index
**Formula**:
$$
SAVI = \frac{(NIR - R) \times (1 + L)}{NIR + R + L}
$$
where typically \(L=0.5\).

**Range:** from -1 to +1  
**Description:** Minimizes soil background effects, ideal for vegetation monitoring in sparse or semi-arid regions. Higher values represent healthier vegetation.
![Spectral Indice Example 13](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image24.png)
SAVI visualized image, Italy. Acquired on 25.05.2020, processed by Sentinel Hub. Source: https://custom-scripts.sentinel-hub.com/custom-scripts/sentinel-2/savi/

---

### 8. **NBR** - Normalized Burn Ratio
**Formula**:
$$
NBR = \frac{NIR - SWIR}{NIR + SWIR}
$$
**Range:** from -1 to +1  
**Description:** Used to assess burned areas and vegetation recovery post-fire. Lower or negative values indicate burned areas; higher positive values suggest healthy vegetation.

![Spectral Indice Example 14](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image25.png)
This image displays a (left) Landsat Surface Reflectance (SR) and (right) the SR-derived Landsat Surface Reflectance Normalized Burn Ratio (NBR). Source: www.usgs.gov


## 3. Land Use/Land Cover Classification (LULC)


**What is Land Cover Classification?**

Land cover classification is the process of assigning each pixel in a satellite image to a specific class, based on its characteristics. Typically, classification is done by comparing spectral reflectance patterns across different land-use categories. The result is a thematic map illustrating different land cover types.

**Example classification map:**

![LULC 1](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image26.png)

*Source: [Natural Resources Canada](https://natural-resources.canada.ca/maps-tools-publications/satellite-elevation-air-photos/image-classification-analysis)*

---

## 🎯 **Two Main Methods of Land Cover Classification**

### 1. **Supervised Classification**

In supervised classification, the user selects example areas (known as training sites), each representing specific land cover classes. The algorithm analyzes the statistical properties of these samples to classify the entire image.

**Common Algorithms:**
- Maximum Likelihood
- Minimum Distance
- Random Forest (RF)
- Support Vector Machine (SVM)

**Supervised Classification example:**

![LULC 2](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image27.png)

*Source: [Natural Resources Canada](https://natural-resources.canada.ca/maps-tools-publications/satellite-elevation-air-photos/image-classification-analysis)*

---

### 2. **Unsupervised Classification**

In unsupervised classification, the algorithm automatically groups pixels with similar spectral properties into clusters. After the algorithm generates these clusters, the user interprets them and assigns appropriate land cover classes.

**Common Algorithms:**
- K-means
- ISODATA

**Unsupervised Classification example:**

![LULC 3](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image28.png)

*Source: [Natural Resources Canada](https://natural-resources.canada.ca/maps-tools-publications/satellite-elevation-air-photos/image-classification-analysis)*

---

## 📊 **Accuracy Assessment**

The accuracy of classification maps is evaluated through confusion matrices, which include metrics such as:

- **Overall Accuracy (OA)**: Percentage of correctly classified pixels.
- **Producer’s Accuracy (PA)**: Accuracy from the perspective of the map producer (precision).
- **User’s Accuracy (UA)**: Reliability from the user’s perspective.
- **Kappa Coefficient**: Measures agreement between the classification and ground-truth data.

---

## 🛰️ **Applications**

Land cover classification is useful for:

- Detecting and analyzing land cover changes
- Environmental monitoring
- Analyzing urbanization and impermeable surfaces
- Agricultural mapping and crop classification


