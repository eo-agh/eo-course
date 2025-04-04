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

![Remote Sensing Example 5](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image6.jpg)  
Landsat Imagery Comparison of a Wildfire Scene: True Color RGB (left), False Color RGB (right). Source: NASA

The image on the left is the visible true color image of a wildfire. Smoke is obscuring the burned area. RGB Imagery Color Components to Wavelengths: Red = 0.66 µm, Green = 0.55 µm, Blue = 0.47 µm.

To "see through” the smoke, we can use the shortwave infrared (SWIR) and near-infrared (NIR) channels. In the false color image on the right for the same fire event, the areas in purple coloring stands out and represents land that has been burned. Even though we can see through the smoke, you can still see shades of smoke in the right image as dark smudges. Image Color to Wavelength: Red = 1.6 µm (Shortwave Infrared), Green = 1.2 µm (Near-Infrared), Blue = 2.1 µm (Shortwave Infrared).

Alternatively, when using an RGB imagery product, each pixel contains a red, green, and blue color component toward the final pixel color. A satellite band or band difference is used within each color component of the RGB in order to identify multiple geophysical parameters within one image (i.e., cloud thickness, phase, and height all within the same image).

![Remote Sensing Example 5](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image7.jpg)  
Source: Himawari-8 AHI

Then, the geophysical parameter range is scaled between black (i.e., no color) to the maximum color intensity per RGB component (i.e., full red, full green, or full blue).

![Remote Sensing Example 5](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image8.jpg)  
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

## 2.1 Example Spectral Indices that will be covered in this lecture

- **NDVI** - Normalized Difference Vegetation Index
- **NDTI** - Normalized Difference Turbidity Index
- **NDCI** - Normalized Difference Chlorophyll Index
- **FAI** - Floating Algae Index
- **AFAI** - Alternate Floating Algae Index
- **NDAVI** - Normalized Difference Aquatic Vegetation Index
- **EVI** - Enhanced Vegetation Index
- **SAVI** - Soil-Adjusted Vegetation Index
- **NBR** - Normalized Burn Ratio 

In the following indices, the formulas use letter symbols to represent the reflectance values in specific spectral channels - for example, R represents the reflectance in the red channel, while NIR denotes that in the near-infrared channel, among others. These equations are general and not tied to images from any particular satellite. To calculate any given coefficient in practice, one must substitute the appropriate channel that covers the required wavelength range for the specific satellite being used. Typically, these formulas are simple algebraic expressions that have been refined over years of scientific research to highlight certain land cover types, such as vegetation, and to assess its condition.

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

![Spectral Indice Example 3](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image14.png)
Source credit: Robert Simmon

**NDVI and seasonality**

Remote sensing is used to track the seasonal changes in vegetation. Monthly NDVI images from MODIS or Landsat can be used to monitor phenology.

![Spectral Indice Example 3](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture2_image15.png)