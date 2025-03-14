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

### 🔄 3.4 Wave Behaviors  

When electromagnetic waves interact with different materials, they exhibit **predictable behaviors**:  

1️⃣ **Reflection** – The wave bounces off a surface (important for optical remote sensing).  
2️⃣ **Absorption** – The wave's energy is absorbed by the material.  
3️⃣ **Scattering** – The wave changes direction randomly (e.g., atmospheric scattering).  
4️⃣ **Transmission** – The wave passes through the material without being absorbed.  
5️⃣ **Emission & Re-emission** – The material releases stored energy as electromagnetic radiation.  

These behaviors are critical in **remote sensing**, as they determine how energy interacts with Earth's surface and atmosphere, affecting how we interpret satellite imagery.  

![Wave Behaviors ](https://raw.githubusercontent.com/eo-agh/eo-course/main/docs/assets/images/lecture1_image6.jpg)  

---

## 🔜 Next Sections  

In the following sections, we will explore:  

➡️ **[Atmospheric Effects](#4-atmospheric-effects)**  
➡️ **[Passive vs. Active Imaging](#5-passive-vs-active-imaging)**  
➡️ **[Resolutions - Imaging Properties](#6-resolutions-imaging-properties)** 

---

## 🔜 Next Sections  

In the following sections, we will explore:  

➡️ **[Electromagnetic Radiation (EMR)](#2-electromagnetic-radiation-emr)**  
➡️ **[Atmospheric Effects](#3-atmospheric-effects)**  
➡️ **[Passive vs. Active Imaging](#4-passive-vs-active-imaging)**  
➡️ **[Resolutions - Imaging Properties](#5-resolutions-imaging-properties)**  

Stay tuned! 🚀  
