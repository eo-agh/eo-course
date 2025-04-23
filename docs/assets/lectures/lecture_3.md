# 📡 Lecture 3: Satellite Image Preprocessing – Fundamentals

## 🛰️ From Radiation to Usable Data: The Basics

The extraction of information from digital remote sensing images is a multistep process. It starts from the moment electromagnetic radiation hits the sensor and ends with a final product ready for interpretation.

The electromagnetic energy received by a satellite sensor (expressed in W/m²/sr) is converted into digital values using calibration curves. These values are stored as a sequence of bits and are referred to as **Digital Numbers (DN)**. Each DN value is proportional to the amount of energy received by the sensor.

To visualize or process this data, it must first be transformed into a **matrix of pixels**, where each pixel holds a DN value. 

![DN Example](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image1.jpg)  


The structure of a digital image is defined by its:

- **Spectral resolution**: number of bands in which radiation is recorded  
- **Radiometric resolution**: number of bits used to encode each pixel (e.g. 8-bit, 16-bit)  
- **Spatial resolution**: the physical size of the area represented by a pixel  
- **Temporal resolution**: how frequently data is acquired over the same area

---

## 🔧 Preprocessing: Radiometric, Geometric and Atmospheric Corrections

Before analysis, satellite images require **preprocessing**, which includes:

- **Radiometric correction**: transforms DN values into physical units such as reflectance, emissivity, or backscatter
- **Geometric correction**: aligns the image to a coordinate system (e.g., UTM)
- **Atmospheric correction**: removes the effects of the atmosphere (e.g., haze, scattering, absorption) to retrieve surface reflectance

## 🔍 Visual Interpretation and Index Calculations

Corrected images can be used for:

- Creating **false color composites**
- Interpreting features visually
- Calculating spectral indices (NDVI, NDWI, NDSI) for:
  - Vegetation monitoring
  - Water and snow analysis
  - Urbanization tracking

---

###  Geometric Correction – Detailed Overview

Geometric correction is a preprocessing step in satellite image analysis that addresses **spatial distortions** inherent in raw imagery. These distortions arise from several factors:

####  Sources of Geometric Distortion:
- Earth's curvature and rotation
- Sensor viewing geometry and motion
- Satellite orbital drift
- Terrain-induced displacements (parallax)
- Platform instability (e.g., roll, pitch, yaw of satellite)

Without correction, features in an image may appear shifted, rotated, stretched, or compressed, and their positions may not match geographic coordinates or maps.

### 📍 Objective of Geometric Correction

The main goal is to transform the image from its original **pixel coordinate system** (row/column) into a **map coordinate system** (e.g., UTM, WGS84, PL-1992) so that:

- Pixels correspond to real-world locations
- The image can be used with other GIS datasets
- Distances, areas, and directions are meaningful


### 🔁 Key Steps in Geometric Correction

#### 1. **Georeferencing**
Aligning the image to a map projection using reference points.

- Done using:
  - **Orbital metadata**: Satellite ephemeris + attitude
  - **Ground Control Points (GCPs)**: Known locations in both image and geographic space (e.g. road intersections, building corners)
  
![GCP](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image3.jpg)  
Credits: Daniel Moraite, https://daniel-moraite.medium.com/georeferencing-satellite-images-using-machine-learning-8f469f6e614


#### 2. **Coordinate Transformation**
A **mathematical function** is used to convert image coordinates (row, col) to ground coordinates (X, Y). Common transformations include:

- **Affine transformation** – allows translation, rotation, and scaling  
- **Polynomial transformations** – 2nd or 3rd order to handle more complex distortions  
- **RPC (Rational Polynomial Coefficients)** – model-based transformation used in high-resolution imagery
  
![Affine](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image4.png)  
Credits: Esri (2023)

#### 3. **Resampling**
Once transformation is applied, pixel values must be interpolated into a new, regular grid.

Most of the projected raster elements of the new image will not match precisely with raster elements in the original image. Since raster data are stored in a regular row–column pattern, we need to calculate DNs for the pixel pattern of the corrected image intended. This calculation is performed by interpolation. This is called resampling of the original image.

📌 Common resampling methods:

| Method | Description | Use Case |
|--------|-------------|----------|
| **Nearest Neighbor** | Assigns value of closest input pixel | Preserves DN for classification |
| **Bilinear** | Weighted average of 4 neighboring pixels | Smooths image, good for visualization |
| **Cubic Convolution** | Uses 16 neighboring pixels | Best for preserving edges in continuous data |

![NN](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image6.jpg)  
Credits: https://ltb.itc.utwente.nl/498/concept/81586

For resampling, we usually use very simple interpolation methods, the main ones being nearest neighbour, bilinear, and bicubic interpolation (Figure 2). Consider the green grid to be the output image to be created. To determine the value of the centre pixel (bold), in nearest neighbour interpolation the value of the nearest original pixel is assigned, i.e. the value of the black pixel in this example. Note that the respective pixel centres, marked by small crosses, are always used for this process. In bilinear interpolation, a linear weighted average is calculated for the four nearest pixels in the original image (dark grey and black pixels). In bicubic interpolation a cubic weighted average of the values of 16 surrounding pixels (the black and all grey pixels) is calculated. Note that some software uses the terms “bilinear convolution” and “cubic convolution” instead of the terms introduced above.

The choice of the resampling algorithm depends, among other things, on the ratio between input and output pixel size and the intended use of the resampled image. Nearest neighbour resampling can lead to the edges of features being offset in a step-like pattern. However, since the value of the original cell is assigned to a new cell without being changed, all spectral information is retained, which means that the resampled image is still useful in applications such as digital image classification. The spatial information, on the other hand, may be altered in this process, since some original pixels may be omitted from the output image, or appear twice. Bilinear and bicubic interpolation reduce this effect and lead to smoother images. However, because the values of a number of pixels are averaged, radiometric information is changed.

![NN](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image7.jpg)  


### Output of Geometric Correction

The final product is an image:
- **Ortho-rectified** (corrected for terrain distortions using DEM)
- **Georeferenced** (aligned to geographic grid)
- With a **map projection** (e.g., UTM, EPSG codes)
- Usable in GIS and for further remote sensing analysis


![Geometric Correction](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image8.jpg)  

Credits: Wong, Man & Zhu, Xiaolin & Abbas, Sawaid & Kwok, Coco Yin Tung & Wang, Meilian. (2021). Optical Remote Sensing. 10.1007/978-981-15-8983-6_20. 


### Tip: Orthorectification vs. Georeferencing

Orthorectification is a process that corrects geometric distortions in satellite imagery, ensuring each point is represented as if it were captured directly below the sensor (nadir view). This process eliminates distortions caused by sensor tilt, terrain relief, and the curvature of the Earth, making the image scale uniform and aligned with the ground. 

| Term | Description |
|------|-------------|
| **Georeferencing** | Aligns image to geographic coordinates using GCPs or metadata |
| **Orthorectification** | Also removes terrain-induced distortions using DEM |

> Most modern satellite products (e.g. Landsat L1T, Sentinel-2 L1C) are already orthorectified.

![Orto](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image8.jpg)  

### Practical Example

An image acquired by Sentinel-2 (L1C level):
- Has been geometrically corrected using orbital metadata and terrain models
- Delivered in UTM projection (EPSG:32633 for Poland)
- Ready for pixel-based analysis, time series, or mosaicking

### 🔍 Summary

- Geometric correction ensures spatial accuracy of satellite imagery
- It aligns raw data to geographic coordinates, enabling integration with maps and other datasets
- Essential for any analysis involving change detection, mapping, or measurement
- Modern sensors often deliver geometrically corrected products, but users must always verify projection, resolution, and alignment

---

###  Radiometric Correction – Detailed Overview

Radiometric correction is a key preprocessing step that transforms raw digital values (DN – Digital Numbers) into physical units that describe the energy interaction between Earth's surface and the sensor.

### 🎯 Objective

The goal is to:
- Convert raw DN values into **spectral radiance** $$L_\lambda$$
- Convert radiance into **reflectance** (specifically, **Top-of-Atmosphere reflectance** $$\rho_{TOA}$$)  
- (Optionally) Perform atmospheric correction to obtain **Surface Reflectance** $$\rho_{SR}$$ 

###  What is Radiance?

Radiance is the variable directly measured by remote sensing instruments. Basically, you can think of radiance as how much light the instrument "sees" from the object being observed. When looking through an atmosphere, some light scattered by the atmosphere will be seen by the instrument and included in the observed radiance of the target. An atmosphere will also absorb light, which will decrease the observed radiance. Radiance most often has units of watt/(steradian/square meter).

**Radiance** \((L_\lambda)\) is the amount of electromagnetic energy received by the sensor **per unit area**, **per unit solid angle**, and **per wavelength**:

$$
L_\lambda \; \left[ \frac{W}{m^2 \cdot sr \cdot \mu m} \right]
$$

Where:
- $$W$$ = watts (energy per second)  
- $$m^2$$ = square meters of surface  
- $$sr$$ = steradian (solid angle unit)  
- $$\mu m$$ = micrometers (wavelength band) 

![TOA](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image9.png)  
Credits: Mathworks

Radiance is computed using **sensor-specific calibration coefficients** (gain and offset), provided in the metadata of the satellite image (e.g., MTL file for Landsat):

$$
L_\lambda = M_L \cdot \text{DN} + A_L
$$

Where:
- $$M_L$$ = radiance multiplicative scaling factor  
- $$A_L$$ = radiance additive scaling factor  
- $$DN$$ = raw digital number  


> These calibration coefficients are specific for each band and sensor.

### 🌍 What is Reflectance?

Reflectance is the ratio of the amount of light leaving a target to the amount of light striking the target. It has no units. If all of the light leaving the target is intercepted for the measurement of reflectance, the result is called "hemispherical reflectance."

**Reflectance** is the ratio of reflected to incoming solar radiation. It is **dimensionless** and normalized between 0 and 1:

$$
\rho = \frac{\text{Reflected Energy}}{\text{Incoming Energy}}
$$

TOA reflectance accounts for:
- Variation in solar irradiance by wavelength
- Solar zenith angle
- Earth–Sun distance

Reflectance (or more specifically hemispherical reflectance) is a property of the material being observed. Radiance, on the other hand, depends on the illumination (both its intensity and direction), the orientation and position of the target and the path of the light through the atmophere. With effort, many of the atmospheric effects and the solar illumination can be compensated for in remote sensing data. This yields something which is called "apparent reflectance," and it differs from true reflectance in that shadows and directional effects on reflectance have not been dealt with. Many people refer to this as "reflectance."

**For many applications, radiance, reflectance, and apparent reflectance can be used interchangibly. However, since reflectance is a property of the target material itself, you will get the most reliable (and repeatable) vegetation index values using reflectance. Apparent reflectance is adequate in many cases.**

###  TOA Reflectance Equation

Once radiance is computed, we normalize it to solar geometry and solar energy to get TOA reflectance:

$$
\rho_{TOA} = \frac{\pi \cdot L_\lambda \cdot d^2}{ESUN_\lambda \cdot \cos(\theta_s)}
$$

**Where:**

| Symbol             | Meaning                                                                 |
|--------------------|-------------------------------------------------------------------------|
| $$\pi$$            | Mathematical constant (~3.1416), used to convert radiance to hemispherical reflectance |
| $$L_\lambda$$      | Spectral radiance at the sensor (from DN)                               |
| $$d$$              | Earth–Sun distance in astronomical units (AU), varies daily             |
| $$ESUN_\lambda$$   | Exoatmospheric solar irradiance for each band (provided in satellite documentation) |
| $$\theta_s$$       | Solar zenith angle (angle between sun and vertical at image location)   |


📌 The solar zenith angle and Earth–Sun distance are available in metadata or can be calculated from the image acquisition date and location.

**Example Values (for Landsat 8)**

| Parameter         | Example Band 4 (Red) Value         |
|-------------------|------------------------------------|
| $$ESUN_\lambda$$  | 2067 W/m²/μm                       |
| $$d$$ (June)      | ~0.967 AU                          |
| $$\theta_s$$      | 35° (varies with location/time)    |



### Radiance vs. Reflectance

Reflectance (or more specifically hemispherical reflectance) is a property of the material being observed. Radiance, on the other hand, depends on the illumination (both its intensity and direction), the orientation and position of the target and the path of the light through the atmophere. With effort, many of the atmospheric effects and the solar illumination can be compensated for in remote sensing data. This yields something which is called "apparent reflectance," and it differs from true reflectance in that shadows and directional effects on reflectance have not been dealt with. Many people refer to this as "reflectance."

For many applications, radiance, reflectance, and apparent reflectance can be used interchangibly. However, since reflectance is a property of the target material itself, you will get the most reliable (and repeatable) vegetation index values using reflectance. Apparent reflectance is adequate in many cases.

###  Why Apply Radiometric Correction?

- **DNs are sensor-specific** and not comparable across images
- **Radiance and reflectance are physical**, standardized units
- Required for:
  - Multi-temporal studies (e.g., vegetation trends)
  - Multi-sensor analysis
  - Deriving biophysical parameters

### 🛠️ Tools and Platforms

| Platform         | Output           | Notes |
|------------------|------------------|-------|
| Google Earth Engine | `TOA` or `SR` collections | Sentinel-2, Landsat |
| SNAP Toolbox     | TOA or SR        | ESA product processor |
| Python (rasterio, numpy) | Manual implementation | Needs metadata access |

###  Summary

Radiometric correction consists of:

1. **DN → Radiance** using gain/offset from metadata  
2. **Radiance → TOA Reflectance** using solar geometry  
3. (Optional) **TOA → Surface Reflectance** using atmospheric correction models  

This process is crucial for ensuring that reflectance values are **physically meaningful** and **comparable across space and time**.

---

## 🌤️ Atmospheric Correction in Remote Sensing

### Why atmospheric correction?

Atmosphere causes **scattering**, **absorption**, and **refraction** of solar radiation. These effects distort the true signal received by the satellite, especially in blue and near-infrared bands. As a result, the reflectance recorded at the satellite sensor (TOA) **does not represent the real surface conditions**.

Atmospheric correction is essential when performing:

- Multi-temporal or seasonal comparisons
- Biophysical parameter estimation (e.g., LAI, FAPAR)
- Vegetation or water indices (e.g., NDVI, NDWI)

### TOA vs. SR Reflectance

| Term | Description |
|------|-------------|
| **TOA Reflectance** | Top-of-Atmosphere reflectance – includes atmospheric effects |
| **SR (Surface Reflectance)** | Bottom-of-Atmosphere reflectance – after removing atmospheric distortion |

TOA radiance is every light which reflects off the planet as seen from space measured in radiance units.
If you look at the planet from space (or if an instrument sensor takes an image) you see what's on the surface, but what you see of the surface it is foggy and bluish. That's because you see (or the sensor registers) mix of light reflected off the surface and off the atmosphere. In fact in the blue region of visible light, greater part of the light comes from atmosphere than from the surface.

Atmospheric correction is then a method how to try to remove influence of just that portion of light reflected off atmosphere on the image and preserve the part reflected off the surface below (simplified to get the idea, because atmosphere does more than just reflecting part of the incoming light).

This way you get BOA (bottom of atmosphere) or surface radiance. The same applies to TOA and BOA/surface reflectance.

![TOA vs SR](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image10.jpg)  
Credits: Masek et al. (2006) A Landsat Surface Reflectance Data Set for North America, 1990–2000

> TOA values tend to be higher and affected by haze, water vapor, and aerosols. SR reflectance is essential for **accurate, quantitative analysis**.


###  Step 1 – Compute TOA Reflectance from Radiance

Before correcting to Surface Reflectance (SR), we first compute **Top-of-Atmosphere Reflectance (TOA)** from spectral radiance (see **Radiometric correction** section)

>  TOA reflectance is standardized across dates and locations, but still includes **atmospheric distortion** – hence the need for further correction to SR!

###  Step 2 – Correct TOA to Surface Reflectance (SR)

Once we have TOA reflectance, we apply an atmospheric correction model to obtain **true surface reflectance**:

$$
\rho_{SR} = \frac{\pi \cdot (L_\lambda - L_p)}{T_z \cdot (E_{down} + ESUN_\lambda \cdot \cos(\theta_s) \cdot T_n)}
$$

This removes:
- $$L_p$$: path radiance (backscatter from atmosphere)  
- $$T_z$$, $$T_n$$: atmospheric transmittance (upward/downward)  
- $$E_{down}$$: diffuse irradiance from the sky  
  

### 🛠️ Correction Methods

There are several methods to perform atmospheric correction, grouped into two broad categories:

#### 🔹 Empirical Method – DOS (Dark Object Subtraction)

**Type:** Empirical  
**Idea:** Assumes that dark objects (e.g., water, deep shadows) should have near-zero reflectance. Any signal from them is due to atmospheric scattering and should be subtracted.

**Steps:**
1. Find minimum DN (or radiance) in each band.
2. Subtract this value from all pixels (assuming it's path radiance).

**Pros:**  
- Simple, fast, and requires no external data

**Cons:**  
- Low accuracy  
- Assumes perfect dark objects are present  
- Not suitable for precise or temporal analysis

Used in: **QGIS SCP**, basic correction pipelines

---

#### 🔹 Physical Model – 6S (Second Simulation of a Satellite Signal)

**Type:** Radiative transfer model  
**Idea:** Simulates light scattering and absorption through the atmosphere using real atmospheric parameters.

**Inputs Required:**
- Aerosol Optical Thickness (AOT)  
- Water vapor and ozone content  
- Solar and view geometry  
- Sensor-specific response functions

**Pros:**  
- Accurate and sensor-specific  
- Suitable for quantitative applications

**Cons:**  
- Requires atmospheric data  
- More complex to implement

Used in: **ENVI FLAASH**, **Py6S**, **Snap**, research workflows

---

#### 🔹 Multi-temporal + Physical – MAJA

**Type:** Hybrid (temporal + physical model)  
**Idea:** Uses past cloud-free observations and physical modeling for better correction over time series.

**Features:**
- Combines radiative transfer with multi-date cloud/shadow analysis  
- Uses DEM (e.g., SRTM) for topographic correction  
- Supports Sentinel-2 and SPOT-6/7

**Pros:**  
- Very robust for time-series  
- Cloud-resistant and topography-aware

**Cons:**  
- Requires multiple scenes  
- Heavier computational pipeline

Used in: **THEIA**, **CNES workflows**, some GEE L2A products

---

### 🧭 Summary Table – Methods Compared

| Method | Type         | Accuracy | Data Required | Best For |
|--------|--------------|----------|---------------|----------|
| **DOS** | Empirical     | ⭐        | None          | Visualization, quick tests |
| **6S**  | Physical model | ⭐⭐⭐⭐     | AOT, water vapor, geometry | Research, accurate NDVI, indices |
| **MAJA**| Physical + temporal | ⭐⭐⭐⭐⭐ | Time series, DEM | Sentinel-2 time series, long-term monitoring |


### When is SR necessary?

| Use Case               | TOA OK? | SR Needed? |
|------------------------|---------|-------------|
| Visualization          | ✅ Yes  | ❌ No        |
| NDVI, NDWI analysis    | ❌ No   | ✅ Yes       |
| Change detection       | ❌ No   | ✅ Yes       |
| Machine learning input | ❌ No   | ✅ Yes       |

-

### 🖼️ Example: TOA vs. SR Comparison

![TOA vs SR](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image11.jpg)  
Credits: USGHS


> **Left**: TOA reflectance affected by haze and atmosphere  
> **Right**: SR reflectance, corrected and ready for NDVI/analysis


## 🔢 Processing Levels Overview

| Level | Description |
|-------|-------------|
| **0** | Raw DN |
| **1A** | Radiometrically calibrated, uncorrected geometry |
| **1C** | TOA reflectance, orthorectified |
| **2A** | SR, atmospheric correction applied |
| **3+** | Final maps, indices, classification results |

---

## 🖼️ Pan-Sharpening (Optional Enhancement)

### What is panchromatic image?

A panchromatic image uses a single band that combines Red, Green, and Blue bands, allowing for a greater spatial resolution. The resulting image does not contain any wavelength-specific information.

### What is Pan-Sharpening?

**Pan-sharpening** is a remote sensing technique that **fuses a high-resolution panchromatic (PAN) image** with **lower-resolution multispectral (MS) bands** to produce a **sharper, high-resolution color image**.

The goal is to combine:
- **Geometric detail** from the PAN band  
- **Spectral (color) fidelity** from the MS bands

This results in a visually rich image that preserves both spatial detail and color information.

### How It Works

Let’s say:
- PAN band has **15 m resolution**
- RGB bands (MS) have **30 m resolution**

Pan-sharpening increases the resolution of the RGB image to match that of the PAN band (15 m), producing a high-resolution color composite.

![Pansharpening](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture3_image12.gif)  

Algorithms often used:
- Brovey Transform  
- Gram-Schmidt Spectral Sharpening  
- Principal Component Analysis (PCA)  
- Intensity-Hue-Saturation (IHS) fusion  
- Simple Mean/Weighted Average

### Why Use Pan-Sharpening?

| Application | Benefit |
|-------------|---------|
| **Urban studies** | Visualize buildings, roads, rooftops clearly |
| **Change detection** | Identify construction, infrastructure evolution |
| **Cartographic mapping** | Produce high-quality true/false color maps |
| **Monitoring** | Better delineation of field boundaries, coastlines |



### 🎨 Example: Landsat 8

- **Band 8** (PAN) → 15 m  
- **Bands 4-3-2** (RGB) → 30 m  
→ Use pan-sharpening to generate 15 m RGB composite.

Example in `rasterio` and `NumPy` (simplified approach):

```python
import numpy as np
import rasterio

# Load PAN and RGB bands
with rasterio.open("B8_pan.tif") as pan_src:
    pan = pan_src.read(1).astype(np.float32)

with rasterio.open("B4_red.tif") as r_src:
    r = r_src.read(1).astype(np.float32)
with rasterio.open("B3_green.tif") as g_src:
    g = g_src.read(1).astype(np.float32)
with rasterio.open("B2_blue.tif") as b_src:
    b = b_src.read(1).astype(np.float32)

# Simple mean-based pan-sharpening (just for demo)
def pansharpen(pan, r, g, b):
    intensity = (r + g + b) / 3
    r_sharp = r * (pan / intensity)
    g_sharp = g * (pan / intensity)
    b_sharp = b * (pan / intensity)
    return r_sharp, g_sharp, b_sharp

r_ps, g_ps, b_ps = pansharpen(pan, r, g, b)
```

>  For real-world applications, use advanced methods (e.g., `gdal_pansharpen.py`, Orfeo Toolbox, or ENVI).

---

### Limitations

- Can distort **spectral accuracy** – not suitable for quantitative analysis  
- Not a substitute for real high-res multispectral sensors  
- Performance varies depending on land cover and method used

---

###  Summary

| ✅ Pros                            | ❌ Cons                            |
|----------------------------------|-----------------------------------|
| Enhanced visual quality          | May distort spectral signatures   |
| Reveals fine-scale urban details | Not ideal for index calculations  |
| Great for map production         | Requires careful method selection |

---

### 🗺️ Pan-sharpened Composite Example

![Pan-sharpened urban image](https://www.researchgate.net/profile/Masroor-Ahmed-9/publication/349845964/figure/fig4/AS:1004562200281090@1614932119782/A-pansharpened-false-color-composite-using-Landsat-8-Oli-data-and-Brovey-Transform.png)

> *False-color pan-sharpened image from Landsat 8 – enhanced building visibility (Ahmed et al., 2021)*


##  Summary

- Satellite images must be radiometrically, geometrically and atmospherically corrected
- TOA → SR correction is essential for quantitative use
- Various methods (model-based, empirical) are available
- Understanding processing levels helps in selecting appropriate datasets

---

### 📚 References

- Landsat 8 Handbook (NASA, 2020)  
- Chander et al. (2009). Summary of current radiometric calibration coefficients for Landsat MSS, TM, ETM+
- Vermote et al. (1997). Second Simulation of the Satellite Signal in the Solar Spectrum (6S)
- Chavez (1988). Improved Dark Object Subtraction  
- Vermote et al. (1997). 6S Model  
- Hagolle et al. (2015). MAJA atmospheric correction  
- ESA Sentinel-2 Handbook  
- Py6S Documentation: https://py6s.readthedocs.io  
- MAJA: https://maja.readthedocs.io  


