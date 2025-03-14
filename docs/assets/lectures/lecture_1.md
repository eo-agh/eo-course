# 🛰️ Lecture 1: Fundamentals of Remote Sensing  

## 🎯 Learning Objectives  

By the end of this lecture, you will understand:  

✅ **[What is Remote Sensing](#1-what-is-remote-sensing)** and its importance in Earth observation  
✅ **[The role of electromagnetic radiation (EMR)](#2-electromagnetic-radiation-emr)** in remote sensing  
✅ **[How the atmosphere affects remote sensing data](#3-atmospheric-effects)**  
✅ **[The difference between passive and active remote sensing systems](#4-passive-vs-active-imaging)**  
✅ **[Key imaging properties](#5-resolutions-imaging-properties)**, including spatial, spectral, radiometric, and temporal resolution  

---

## 📌 Lecture Topics Overview  

1️⃣ **[What is Remote Sensing?](#1-what-is-remote-sensing)**  
2️⃣ **[Electromagnetic Radiation (EMR)](#2-electromagnetic-radiation-emr)**  
3️⃣ **[Atmospheric Effects](#3-atmospheric-effects)**  
4️⃣ **[Passive vs. Active Imaging](#4-passive-vs-active-imaging)**  
5️⃣ **[Resolutions - Imaging Properties](#5-resolutions-imaging-properties)**  

---

## 1️⃣ What is Remote Sensing? {#1-what-is-remote-sensing} 🌍  

Remote sensing is the **process of collecting information** about objects from a distance, without the need for physical contact. It is both a **science and an art**, as it involves obtaining and interpreting data about an object, area, or phenomenon through measurements made by instruments that are not in direct contact with the subject (Lillesand et al., 2015).  

![Remote Sensing Illustration](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image1.jpg)  

### 👁️ 1.1 Detecting Light  

A simple example of remote sensing is **human vision**. Our eyes detect red, green, and blue light, and our brain processes these signals into the full range of visible colors. **Artificial remote sensing systems**, such as cameras, satellites, and sensors, work in a similar way—by detecting and interpreting different wavelengths of electromagnetic radiation.  

### 🛰️ 1.2 How Remote Sensing Works  

Remote sensing allows scientists to monitor and analyze **Earth’s surface and atmosphere** by measuring the **reflected or emitted radiation** from various objects.  
Drones, airplanes, and satellites equipped with specialized sensors capture this energy and translate it into usable data.  

Depending on the application, **remote sensing sensors** collect data across different parts of the **electromagnetic spectrum** and at various levels of resolution.  
This helps in characterizing different land areas, water bodies, and atmospheric conditions.  

![Land Cover Example](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image2.png)  

### 🔑 1.3 Essential Elements of Remote Sensing  

To perform remote sensing, three key components are required:  

1️⃣ **A platform** – A carrier for the sensor, such as a satellite, drone, or aircraft.  
2️⃣ **A target** – The object or area being observed (e.g., land surface, ocean, clouds).  
3️⃣ **An instrument** – A sensor designed to detect and capture specific types of energy.  

These instruments analyze different energy sources and provide insights into **environmental changes, land cover, vegetation health, and more**.  

---

## 2️⃣ Remote Sensing Platforms {#2-remote-sensing-platforms}  

Remote sensing platforms refer to the **carriers** that house cameras or sensors for data collection.  
These platforms can be **stationary** (e.g., cameras on tripods) or **mobile** (e.g., drones, aircraft, satellites).  
The choice of platform significantly affects the **type, scale, and frequency** of collected imagery.  

---

### 📌 2.1 Types of Remote Sensing Platforms  

#### 1️⃣ Ground-Based Platforms 🌍  
- Tripods, towers, and vehicles equipped with sensors for close-range remote sensing.  

#### 2️⃣ Aerial Platforms ✈️  
- Drones, airplanes, or balloons that operate within the atmosphere, capturing medium-scale imagery.  

#### 3️⃣ Satellite Platforms 🛰️  
- Orbiting satellites providing large-scale, repetitive coverage of Earth's surface.  

---

### 💰 2.2 Cost vs. Coverage Trade-off  

As a general rule, **higher altitude platforms** tend to be **more expensive** but **cover larger areas more efficiently**.  

- A **handheld camera** is inexpensive but impractical for imaging large areas.  
- A **drone** can capture high-resolution imagery at a regional scale.  
- A **satellite** is costly to launch and maintain but can continuously monitor vast portions of the planet.  

📉 **Resolution Considerations**  
The **farther a platform is from Earth**, the lower the spatial resolution tends to be.  
This means that each pixel in the image represents a larger surface area on Earth.  

![Platform Types](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image3.png)  


## 3️⃣ Electromagnetic Waves {#3-electromagnetic-waves} 🌊  

The application of remote sensing sensors and methods relies on the existence of **electromagnetic (EM) radiation**. Whether the radiation is passively measured (e.g., reflection of sunlight) or actively emitted from an instrument, **remote sensing cannot function without this source of energy**.  

But what exactly are **waves**?  

A **wave** is an undulating motion that transports **energy** in the direction of its propagation. A simple example of natural waves can be seen in **water waves** forming after a stone is thrown into a pond. Similarly, **sound waves** are created when we speak or when a police siren passes by.  

### 🌞 3.1 Electromagnetic Wave Structure  

Radiation from the Sun travels in the form of **electromagnetic waves**, where **electric** and **magnetic fields** are coupled together.  

An **electromagnetic wave** consists of two perpendicular components:  
- **An electric field (E, blue)**
- **A magnetic field (B, red)**  

The **electric field** oscillates in one plane, while the **magnetic field** oscillates at a right angle to it. Both fields propagate at the **speed of light** (~300,000 km/s).  

![Electromagnetic Wave Structure](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image5.gif)  

---

### 📏 3.2 Wave Characteristics  

Electromagnetic waves are described by three fundamental properties:  

1️⃣ **Frequency (ν)** – The number of wave cycles (marked by crests) that pass a point in a given time (usually per second).  
2️⃣ **Wavelength (λ)** – The distance between two successive crests of a wave.  
   - **Wavelength and frequency are inversely proportional**:  
     - Higher frequency → **shorter wavelength**  
     - Lower frequency → **longer wavelength**  
3️⃣ **Amplitude (A)** – The height of the wave from its **rest position** to the **crest** (top) or **trough** (bottom).  
   - **Intensity** (important in remote sensing) is proportional to the square of the amplitude.  

The relationship between these properties can be expressed as:  
\[
\text{frequency} = \frac{\text{speed of light}}{\text{wavelength}}
\]

---

### 🔬 3.3 Energy and Wavelength  

The **energy of a wave** is directly related to its frequency:  

- **Higher frequency = more energy**  
- **Lower frequency = less energy**  

Thus, **waves with longer wavelengths carry less energy**, while **short-wavelength waves (like X-rays) carry more energy**.  

![Electromagnetic Spectrum](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image4.png)  

---



## 3.4 The Spectrum of Electromagnetic Radiation  

Electromagnetic energy travels in **waves** and spans a **broad spectrum** ranging from **very long radio waves** to **very short gamma rays**. The **human eye** can detect only a **small portion** of this spectrum, known as **visible light**.  

Other devices, such as **radios**, **X-ray machines**, and **scientific instruments** used in remote sensing, are capable of detecting different regions of the **electromagnetic spectrum (EMS)**. These instruments allow scientists to study not only **Earth** but also **the solar system** and even **the universe beyond**.  

---

### 📊 3.4.1 Electromagnetic Spectrum Overview  

The figure below illustrates the **different regions of the electromagnetic spectrum**, including their:  
- **Names** (radio waves, microwaves, infrared, visible light, ultraviolet, X-rays, gamma rays)  
- **Wavelengths** (measured in meters, micrometers, or nanometers)  
- **Frequencies** (measured in Hertz)  
- **Energy levels**  

It also highlights the **scale of objects** that can interact with each wavelength and the biological or environmental **influences of different EM radiation types**.  

![EM Spectrum](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image7.jpg)  

---

### 🔬 3.4.2 Wavelength, Frequency, and Energy Relationship  

Now that we have discussed the **fundamental properties of EM waves**, we can explore how **photons** are distributed along the **electromagnetic spectrum (EMS)**.  

We know that:  
- **Wavelength and frequency are inversely related** (shorter wavelength = higher frequency).  
- **Photon energy increases as wavelength decreases**.  

#### **Blackbody Radiation and Temperature Dependence**  

The **temperature of an object** affects the **wavelength of radiation it emits**. The figure above also demonstrates this using a **thermometer**, which shows that:  
- **Hotter objects emit shorter wavelengths** of radiation.  
- **Cooler objects emit longer wavelengths** of radiation.  

This relationship follows **Planck's Law**, which describes the emission of electromagnetic radiation from an idealized **blackbody**. A blackbody is a **theoretical object** that absorbs **all incoming radiation** and emits energy based purely on its temperature.  

For example:  
- The **Sun (5788 K)** emits most of its radiation at **~0.5 × 10⁻⁶ m (500 nm, visible light)**.  
- The **human body (~310 K)** emits most of its radiation at **~10⁻⁴ m (infrared range, ~10 µm)**.  

📌 **Important Note:** In reality, **blackbodies do not exist**—real-world objects always emit slightly less radiation than a perfect blackbody at the same temperature.  


---


### 🌞 3.4.3 The Primary Source of Electromagnetic Radiation {#53-the-primary-source-of-electromagnetic-radiation}  

The primary source of energy received on Earth is electromagnetic radiation emitted from the Sun.  

The Sun’s radiation is reflected and absorbed by the Earth's atmosphere and surface. Satellites carry instruments that measure the electromagnetic radiation reflected or emitted.  

![Prim EM Source](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image8.jpg)  

The Sun emits most of its energy at optical wavelengths, between 0.1 µm to 4 µm. Solar energy, frequently referred to as shortwave radiation, includes ultraviolet, visible, and infrared radiation. In Earth satellite remote sensing, we are mostly concerned with wavelengths from ultraviolet (0.1 µm) through the microwave (100,000 µm).  

![Sun Emission](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image9.jpg)  

---

### 🔬 3.4.4 Absorption in the Atmosphere

Understanding where our atmosphere absorbs different parts of the **electromagnetic radiation (EMR)** is crucial for interpreting signals received by **remote sensing instruments**.  

A key distinction between **atmospheric absorption** and **scattering** is the **effective energy loss** to atmospheric constituents. In absorption, energy is **directly transferred** into molecules in the atmosphere or to the **remote sensing targets**.  

Certain **gases in the atmosphere**, such as:  
- **Ozone (O₃)**  
- **Carbon dioxide (CO₂)**  
- **Water vapor (H₂O)**  

can **absorb energy** and contribute to **warming the planet**.

When electromagnetic waves interact with different materials, they exhibit **predictable behaviors**:  

1️⃣ **Reflection** – The wave bounces off a surface (important for optical remote sensing).  
2️⃣ **Absorption** – The wave's energy is absorbed by the material.  
3️⃣ **Scattering** – The wave changes direction randomly (e.g., atmospheric scattering).  
4️⃣ **Transmission** – The wave passes through the material without being absorbed.  
5️⃣ **Emission & Re-emission** – The material releases stored energy as electromagnetic radiation.  

These behaviors are critical in **remote sensing**, as they determine how energy interacts with Earth's surface and atmosphere, affecting how we interpret satellite imagery.  

![Wave Behaviors ](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/Lecture1_image6.jpg)  

---

### 🌍 3.4.4.1 Atmospheric Windows

From a **remote sensing perspective**, the goal is to use **wavelengths that avoid strong absorption regions** in the atmosphere.  

📌 **Where the atmosphere is highly transmissive to incoming wavelengths, we call these regions "atmospheric windows".**  

The **brown curve** in the diagram below represents the **opaqueness** of the atmosphere.  

- The **big atmospheric windows between 1 mm and 1 m** allow us to operate **microwave remote sensing systems** (e.g., radar sensors).  
- In contrast, **atmospheric windows in the multispectral portions of the EM spectrum** are much **narrower**.  

![Atmospheric Absorption](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image10.jpg)  

---

### 🔄 3.4.4.2 Selecting the Right Remote Sensing Instrument  

When designing or choosing **remote sensing sensors**, it is essential to carefully consider the following three questions:  

1️⃣ **What is the spectral sensitivity of my sensor?**  
   - Does my sensor operate in a wavelength range affected by atmospheric absorption?  

2️⃣ **Which atmospheric windows can be used with this sensor?**  
   - Is my sensor designed to work in regions of high transmissivity?  

3️⃣ **What is the source, magnitude, and composition of the outgoing signal we are aiming to analyze?**  
   - How does the atmosphere influence the signal we receive?  

Selecting an appropriate sensor and **understanding atmospheric absorption** is critical to ensuring the accuracy of **Earth observation data**.  

---

### 🔄 3.4.4.5 Why Is This Important for Remote Sensing?  

Understanding the **electromagnetic spectrum** is crucial for remote sensing because:  
✅ Different materials interact with specific **wavelengths** of radiation.  
✅ Sensors are designed to detect radiation at different **frequencies** (e.g., infrared for vegetation, microwaves for weather radar).  
✅ The **Earth's atmosphere** absorbs certain wavelengths while allowing others to pass through (this is why certain satellites use infrared or microwave sensors to "see" through clouds).  

This knowledge allows us to design **specialized remote sensing instruments** for applications such as:  
🌱 **Vegetation monitoring** (infrared and near-infrared reflectance)  
🏙️ **Urban mapping** (visible and shortwave infrared)  
🌊 **Water quality assessment** (UV and visible light absorption)  
🌎 **Climate studies** (microwave and infrared radiation)  

---

4️⃣ Spectral Signatures {#4-spectral-signatures}  

## 🔍 4.1 What are Spectral Signatures? {#41-what-are-spectral-signatures}  

Different wavelengths of the **electromagnetic spectrum** interact **differently** with various materials on Earth's surface and in the atmosphere.  

Certain **materials and physical properties** have a unique way of interacting with incident radiation. This interaction is called the **spectral response**—how the material reflects, absorbs, or emits radiation.  

📌 **The spectral response of an object is known as its spectral signature.**  

For example:  
- Some materials have a **higher reflectance** at specific wavelengths.  
- The **percent reflectance** is the ratio of **reflected energy** to the total incident energy at a given wavelength.  

### 🔬 Key Concepts  

🟢 **Radiance**: A measure of the power of electromagnetic radiation emitted from an object per unit area for a given wavelength. In the visible spectrum, radiance is also described as the **brightness** of the source. It is directly proportional to **amplitude** (and intensity) of the wave.  

⚪ Surfaces do not only reflect light; they also **partially absorb it**.  

During **absorption**, energy is taken up by the molecules of a material and transformed into **kinetic energy**. This increased molecular movement produces **heat**, which is radiated back to the surroundings.  

📌 **Example:** A **black t-shirt** absorbs more sunlight than a **white t-shirt**, which is why we feel hotter wearing black in summer.  

Albedo measures the **reflective properties** of materials across different spectral ranges:  
- **Albedo = 100%** → No absorption, full reflection.  
- **Albedo = 0%** → No reflection, full absorption.  

| Material           | Albedo (%) |
|-------------------|-----------|
| **Snow**         | 80-90%    |
| **Cloud**        | 60-90%    |
| **Sand**         | 30%       |
| **Meadow**       | 20%       |
| **Forest**       | 5-18%     |
| **Concrete**     | 15%       |
| **Water (low angle)** | 22%   |
| **Water (high angle)** | 5%   |

![Seasonal Albedo Changes](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image12.jpg)

**Surface Albedo**: The fraction of incident radiation that is **reflected by the Earth's surface** for a given location and time.  

<video width="800" controls>
  <source src="https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/videos/lecture1_video1.mp4" type="video/mp4">
</video> 

---

## 💡 4.2 Types of Reflection {#42-types-of-reflection}  

The way **electromagnetic waves** interact with surfaces depends on their **roughness**. There are three main types of reflection:  

![Reflection examples](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image18.gif)

### 1️⃣ **Specular Reflection** (Mirror-like)  
- Occurs when light strikes a **smooth** surface.  
- The **angle of incidence** is equal to the **angle of reflection**.  
- Example: **Glass, still water, metal surfaces**.  

### 2️⃣ **Diffuse Reflection**  
- Happens on **rough** surfaces, scattering light in **all directions**.  
- No clear angle of reflection.  
- Example: **Concrete, vegetation, unpolished wood**.  

### 3️⃣ **Mixed Reflection**  
- The most **common** type in nature.  
- A combination of **specular and diffuse** reflection.  
- Example: **Most natural surfaces like soil, rocks, leaves**.  

---

## 🛰️ 4.3 Remote Sensing and Spectral Signatures {#43-remote-sensing-and-spectral-signatures}  

**Remote sensors** are designed to detect **wavelengths** in particular parts of the **electromagnetic spectrum**. These instruments help **identify objects or materials** based on their spectral signatures.  

Let's examine how different materials on Earth interact with **electromagnetic radiation** and define their unique spectral signatures:  

![Spectral Signatures Example](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image12.jpg)

### 🍃 Vegetation  
- Plants absorb **blue and red light** due to **photosynthesis**.  
- **Peak reflectance** occurs in the **green** region (which is why plants appear green).  
- **Near-infrared (NIR) reflectance** is much **higher** than in the visible spectrum.  

---

### 🌊 Water  
- **Clear water absorbs most radiation**, appearing dark.  
- **Turbid water** reflects **more** light.  
- **Algal blooms increase green reflectance**.  

---

### 🏜️ Soil  
- Soil **moisture content** impacts its spectral signature.  
- **Dry soil** has **higher reflectance** than **wet soil**.  

---

### ❄️ Ice & Snow  
- **Fresh snow has high reflectance** across the visible and NIR regions.  
- **Aged or dirty snow absorbs more radiation**, lowering reflectance.  

---

### ☁️ Atmosphere  
- Atmospheric **gases and particles** scatter and absorb certain wavelengths.  
- Clouds reflect visible light, making them bright in satellite imagery.  

📌 **Understanding atmospheric interference is crucial** for interpreting remote sensing data correctly.

---

## 🎯 4.4 Using Spectral Signatures to Distinguish Materials {#44-using-spectral-signatures-to-distinguish-materials}  

Each material **absorbs and reflects** different **wavelengths** of electromagnetic radiation.  

The **graph below** compares reflectance values across various materials:  

![Spectral Signatures Graph](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image13.jpg)  


# 4️⃣ Spectral Signatures {#4-spectral-signatures}  

## 🛠️ 4.5 How to Measure Spectral Signature? {#46-how-to-measure-spectral-signature}  

To analyze spectral signatures, scientists use **specialized instruments** that measure the **reflectance, absorption, and emission** properties of different materials. There are two main approaches to measuring spectral signatures:  

---

### 🌱 4.5.1 Field Measurements Using a Spectroradiometer  

A **spectroradiometer** is an instrument used in **field conditions** to measure how different surfaces interact with light. These devices capture spectral signatures of vegetation, soil, water, and other materials **directly in their natural environment**.  

📌 **Example: Measuring Spectral Signatures of Vegetation**  
- Used to analyze plant health, chlorophyll content, and stress levels.  
- Helps monitor **photosynthetic activity** by measuring **near-infrared (NIR) reflectance**.  
- Data is used in applications like **precision agriculture, ecosystem monitoring, and climate studies**.  

🔍 **Field Measurement Example:**  

![Field Measurements](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image15.jpg)  

---

### 🧪 4.5.2 Laboratory Measurements Using a Hyperspectral Camera  

In controlled laboratory environments, **hyperspectral cameras** capture spectral signatures with high precision. These cameras analyze **light interactions** across hundreds of spectral bands, allowing for highly detailed material classification.  

📌 **Example: Measuring Spectral Properties of Samples in a Lab**  
- Used for **soil, minerals, plant samples, and industrial materials**.  
- Provides **high spectral resolution** for material classification and chemical analysis.  
- Used in **geology, material science, agriculture, and environmental monitoring**.  

🔍 **Hyperspectral Imaging Examples:**  

![Lab Hyperspectral Camera](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image16.jpg)  
![Lab Hyperspectral Sample](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image17.jpg)  
![Hyperspectral Imaging Output](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image19.png)  

---

## 🎯 Why Is Spectral Signature Measurement Important?  

✅ **Distinguishing materials based on their spectral properties**  
✅ **Identifying plant stress, soil moisture, or water quality changes**  
✅ **Enhancing remote sensing applications in agriculture, geology, and climate science**  
✅ **Calibrating satellite and airborne remote sensing data for improved accuracy**  

---

# 5️⃣ Passive vs. Active Imaging {#5-passive-vs-active-imaging}  

## 🔍 5.1 Passive vs. Active Sensors  

The way a **remote sensing sensor** captures energy is categorized as either **passive** or **active**.  

**Remote sensors detect electromagnetic radiation** to identify physical characteristics of an object. They either:  
✅ **Use an external source of radiation**, most often the Sun (**passive sensors**).  
✅ **Transmit their own energy** toward the object and measure the return (**active sensors**).  

![Passive vs Active sensors](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image22.png)  


📌 **Comparison of Passive and Active Sensors:**  

| Sensor Type  | Energy Source | Day/Night Operation | Weather Dependency | Example Applications |
|-------------|--------------|-------------------|-------------------|--------------------|
| **Passive** | External (e.g., Sun) | Limited at night | Can be affected by clouds | Optical imagery, thermal sensing, vegetation health |
| **Active** | Own energy source | Works day & night | Can operate in all weather conditions | Radar, LiDAR, altimetry |

---

## ☀️ 5.2 Daytime Dependence of Passive Sensors  

### 🌞 5.2.1 The Role of Natural Radiation  

Passive remote sensing **relies solely on naturally occurring radiation**, primarily from the **Sun**. Unlike active sensors, passive instruments **do not emit their own pulses** of electromagnetic energy. This means that:  
- **Passive optical sensors can only acquire data during the day.**  
- **Without natural light, no radiation is reflected back to the sensor, rendering nighttime imaging impossible** (except in thermal infrared).  
- **Atmospheric conditions** (e.g., cloud cover, haze) affect the **amount of sunlight reaching the Earth's surface**, which in turn **impacts image quality**.  

However, **some passive sensors can operate at night**—for example, thermal infrared scanners that measure the **heat emitted from objects** rather than reflected sunlight.  

📌 **Illustration: Conceptual operation of passive and active remote sensing instruments**  

![Passive and Active Remote Sensing](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image20.gif)  

---

## 📡 5.3 Active Sensors  

Active sensors **generate and transmit their own energy** toward a target, then detect the **reflected or scattered return signal**.  

✅ **Advantages of Active Sensors:**  
- Work **independently of sunlight** → Can operate **day and night**.  
- Can **penetrate clouds, smoke, and even vegetation canopies** (especially radar-based sensors).  
- Provide **3D surface mapping capabilities** (e.g., LiDAR, radar altimetry).  

📷 **Examples of Active Sensors:**  
- **Radar (Synthetic Aperture Radar - SAR)** – Used for Earth surface monitoring and disaster response.  
- **LiDAR (Light Detection and Ranging)** – High-precision elevation mapping.  
- **Altimeters** – Measure ocean height and ice sheet thickness.  

---

## 📷 5.4 Types of Passive Remote Sensing Instruments  

Most **passive** remote sensing sensors are classified as either **multispectral (MS)** or **hyperspectral (HS)** instruments.  


![Passive and Active Remote Sensing](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image21.jpg)  

### 🎨 5.4.1 Multispectral Sensors  

**Multispectral remote sensing** records data in **multiple spectral bands** of the electromagnetic spectrum.  
- The first **multispectral satellite**, **Landsat’s Multispectral Scanner (MSS)**, was launched in **1972**.  
- It recorded data in **four spectral bands** (**blue, green, red, and near-infrared**), which were crucial for **vegetation analysis**.  
- Today’s advanced multispectral sensors, such as **Sentinel-2**, provide:  
  - **13 spectral bands**  
  - **High revisit times**  
  - **Spatial resolution up to 10 meters**  

📌 **Multispectral satellites like Sentinel-2 have revolutionized global remote sensing by providing frequent and detailed observations of land surfaces.**  

---

### 🌈 5.4.2 Hyperspectral Sensors  

**Hyperspectral sensors** capture **hundreds** of narrow spectral bands, offering **finer spectral resolution** than multispectral sensors.  
- Instead of just a few bands, hyperspectral sensors collect data across **the entire electromagnetic spectrum**, allowing for **detailed material classification**.  
- **Hyperspectral imaging is particularly useful for:**  
  ✅ Identifying specific minerals, water quality, and vegetation health.  
  ✅ Detecting chemical compositions of materials.  
  ✅ Monitoring environmental changes with greater precision.  

📌 **Comparison of Multispectral vs. Hyperspectral Sensors:**  

| Sensor Type   | Number of Bands | Spectral Band Width | Example Applications |
|--------------|----------------|----------------------|----------------------|
| **Multispectral** | 3-20 | 50-200 nm | Land cover mapping, vegetation health |
| **Hyperspectral** | 100+ | 10-20 nm | Mineral identification, water quality |

🔗 **Explore Interactive Spectral Visualization:**  
For an interactive **visualization of the electromagnetic spectrum**, including spectral characteristics and wavelength manipulation, visit:  
👉 [Interactive EMSpectrum Tool](https://ubcemergingmedialab.github.io/geomatics-textbook/viz/emspectrum-viz/)  

# 6️⃣ Resolutions - Imaging Properties {#6-resolutions-imaging-properties}  

## 📌 6.1 Introduction to Resolutions  

One of the first considerations when using remotely sensed data is **data quality**. In scientific research, good quality data must be **relevant to the scale and time period** of the study. To achieve this, **remote sensing sensors are designed with specific applications in mind** and are characterized by **four key resolutions**:  

1️⃣ **[Spatial Resolution](#61-spatial-resolution)** – Defines the smallest distinguishable detail in an image.  
2️⃣ **[Temporal Resolution](#62-temporal-resolution)** – Refers to how often an area is imaged.  
3️⃣ **[Spectral Resolution](#63-spectral-resolution)** – Determines the number and width of wavelength bands measured.  
4️⃣ **[Radiometric Resolution](#64-radiometric-resolution)** – Defines a sensor’s ability to detect differences in energy intensity.  

Each of these resolutions impacts the **type, accuracy, and usability** of remote sensing data for different applications.  

---

## 📷 6.1 Spatial Resolution {#61-spatial-resolution}  

Spatial resolution refers to the **ground area represented by a single pixel** in an image.  
- A **higher spatial resolution** means **finer details**, as each pixel covers a smaller area on the ground.  
- A **lower spatial resolution** means **coarser details**, with each pixel covering a larger area.  

### 🔍 6.1.1 Pixels and Image Formation  

When a sensor collects data, it captures information from an **area of the Earth's surface**.  
- This area could be as small as **a single tree** or as large as **an entire city**.  
- All electromagnetic radiation (EMR) collected in this area is **averaged into a single pixel value**.  
- An **image** is formed when **multiple pixels are collected over an area**.  

📌 **Illustration: The concept of pixel size and spatial resolution**  

![Spatial Resolution](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image24.jpg)  

### 🏗️ 6.1.2 Factors Affecting Spatial Resolution  

Several factors influence spatial resolution:  
1️⃣ **Field of View (FOV)** – The area observed by the sensor, determined by its **viewing angle** and **altitude**.  
2️⃣ **Instantaneous Field of View (IFOV)** – The area observed by the sensor at the moment a pixel is recorded.  
3️⃣ **Altitude and Orbit** – Satellites at **higher altitudes** have **coarser resolution**, while **low-orbit sensors** capture **finer details**.  

![FOV IFOV](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image26.jpg)  


## 🎭 6.1.3 Mixed Pixels {#66-mixed-pixels}  

### 🔍 What Are Mixed Pixels?  

A **mixed pixel** occurs when a single pixel contains signals from **multiple surface types** rather than representing a single, uniform feature.  

This happens when:  
- The spatial resolution of the sensor is **too coarse** to distinguish fine details.  
- Different land cover types (e.g., vegetation, water, soil) are present **within the same pixel area**.  
- The transition between features (e.g., urban-rural boundaries, coastlines) is gradual rather than distinct.  

📌 **Illustration: Mixed Pixels in Satellite Imagery**  

![Mixed Pixels Example](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image22.jpg)  

---

### 🏗️ 6.1.4 Impact of Mixed Pixels  

Mixed pixels can introduce **errors** in remote sensing analysis, as they:  
✅ Reduce **classification accuracy**, making it difficult to assign a pixel to a single land cover class.  
✅ Cause **spectral mixing**, where the recorded spectral signature is an average of multiple materials.  
✅ Affect **change detection**, making it harder to track specific land cover transitions.  

---

### ⚖️ 6.1.35 Trade-offs in Spatial Resolution  

✅ **Higher spatial resolution** provides **detailed imagery** but requires **more storage and processing power**.  
✅ **Lower spatial resolution** is **easier to process** but may miss **small features**.  

When choosing a **sensor for an application**, scientists balance **detail, processing efficiency, and study area coverage**.  

---

## 🕒 6.2 Temporal Resolution {#62-temporal-resolution}  

Temporal resolution refers to the **time interval between successive observations of the same location**.  

- It can range from **hours to years**, depending on the application, platform and sensor.  
- It is essential for **monitoring changes over time** (e.g., urban growth, deforestation, climate change).  

📌 **Common Temporal Resolutions in Remote Sensing:**  

| Application | Temporal Resolution |
|------------|--------------------|
| **Weather Monitoring** | Hourly |
| **Vegetation Growth & Crop Health** | Daily – Weekly |
| **Urban Expansion Studies** | Annually |
| **Climate Change Analysis** | Decadal |

### 🌍 6.2.1 Revisit Time  

Revisit time is the **interval between consecutive observations of the same location**.  
- **Stationary sensors** (e.g., geostationary satellites) have **short revisit times** (seconds/minutes).  
- **Orbiting sensors** may take **days or weeks** to return to the same location.  

✅ **Some satellites (e.g., Sentinel-2) are designed for high temporal resolution**, ensuring frequent monitoring of Earth's surface.  

---

## 🌈 6.3 Spectral Resolution {#63-spectral-resolution}  

Spectral resolution defines how a **sensor detects electromagnetic radiation (EMR) across different wavelengths**.  

![Spectral resolution](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image27.jpg)  

📌 **Spectral resolution refers to:**  
1️⃣ **The number of spectral bands** a sensor detects.  
2️⃣ **The location of bands along the electromagnetic spectrum**.  
3️⃣ **The width of each spectral band** (narrow vs. wide).  

### 📊 6.3.1 Spectral Bands and Energy Sensitivity  

Each sensor records **specific wavelength ranges**, which determine what features can be observed.  
- **Shorter wavelengths (e.g., blue light)** have **higher energy** and are **easier to detect**.  
- **Longer wavelengths (e.g., thermal infrared, microwave)** require **larger band widths** for effective observation.  

📌 **Example: Landsat Mission Sensors & Spectral Bands**  

Landsat satellites have evolved to include more spectral bands:  
- Landsat 1-5: **Multispectral Scanner System (MSS)**  
- Landsat 4-5: **Thematic Mapper (TM)**  
- Landsat 7: **Enhanced Thematic Mapper Plus (ETM+)**  

📌 **Illustration: Spectral bands of Landsat sensors**  

✅ **Sensors with higher spectral resolution** capture more bands and provide **richer spectral data** for classification.  

---

## 🎨 6.4 Radiometric Resolution {#64-radiometric-resolution}  

Radiometric resolution determines a sensor’s **ability to detect small differences in energy intensity**.  
- Incoming photons pass through a **filter**, allowing only specific wavelengths to reach the detector.  
- The sensor assigns a **digital number (DN)** to each pixel, representing **energy intensity**.  

### 🔢 6.4.1 Bits and Data Storage  

Radiometric resolution is measured in **bits**, which define the number of **discernible energy levels**.  
- **Higher bit depth** = **greater sensitivity to subtle differences**.  

📌 **Common Radiometric Resolutions:**  

| Bit Depth | Number of Discrete Levels | Example Applications |
|----------|--------------------------|---------------------|
| **8-bit** | 256 levels | Standard satellite imagery |
| **12-bit** | 4,096 levels | Advanced environmental monitoring |
| **16-bit** | 65,536 levels | High-precision scientific analysis |

![Radiometric Resolution Example](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image28.jpg)  

The left image is 16-bit radiometric resolution (65,536 discrete shades of grey), the center image is an 8-bit radiometric resolution (256 discrete shades of grey), the right image is 4-bit radiometric resolution (16 discrete shades of grey).

### 🖼️ 6.4.2 Visualization of Radiometric Resolution  

📌 **Illustration: Radiometric Resolution and Data Depth**  

![Radiometric Resolution](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image26.jpg)  

✅ **Higher radiometric resolution** allows for finer distinctions in brightness, improving image quality.  
✅ **However, increasing resolution also increases data storage and processing requirements**.  

---

## 🔄 6.5 Summary: Choosing the Right Resolution  

Each resolution influences **how remote sensing data is collected, processed, and applied**.  

📌 **Key Takeaways:**  
- **Spatial resolution** affects **detail level** – Higher resolution means finer details but larger storage requirements.  
- **Temporal resolution** affects **frequency of observations** – Important for tracking changes over time.  
- **Spectral resolution** affects **wavelength coverage** – Determines how well features can be distinguished.  
- **Radiometric resolution** affects **energy detection sensitivity** – Impacts image clarity and depth.  

✅ **Choosing the right sensor depends on the study's objectives and computational resources.**  

---

# 🎯 Remote Sensing Quiz  

## 🛰️ Identify the Object in the Satellite Image  

The following image is a **satellite image** taken from **Landsat-8**, orbiting **700 km above the ground**.  

### 🔍 Can you identify what is inside the red circle?  

![Landsat-8 Satellite Image](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image25.jpg)  
![Sentinel-2](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image29.jpg)  
![Dove](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image30.jpg)  

