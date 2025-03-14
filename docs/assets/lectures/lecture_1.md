# **🛠️ Lab 0: Environment Setup & Configuration**  

## **1. Objective**  
Before we start working with satellite data, we need to set up the **development environment**.  
This lab focuses on installing and configuring:  
✅ **VS Code & GitHub** for version control.  
✅ **Google Earth Engine (GEE)** for satellite data processing.  
✅ **Google Colab** for cloud-based Python execution.  
✅ **Miniconda & Python libraries** for geospatial analysis.  

---

## **2. Installing the Required Tools**  

### **2.1. Code Editor: Visual Studio Code (VS Code)**  
📌 **Download & Install VS Code**: [VS Code Download](https://code.visualstudio.com/)  

After installation, install the following extensions:  
- **Python Extension** – Enables Python scripting.  
- **Jupyter Extension** – Enables Jupyter Notebook inside VS Code.  
- **GitHub Copilot (Optional)** – AI-powered code assistance.  

---

### **2.2. Git & GitHub Setup**  
We will use GitHub for project version control.  

📌 **Download & Install Git**: [Git Download](https://git-scm.com/downloads)  

📌 **Set up GitHub** (if you don’t have an account, create one at [GitHub](https://github.com/)):  

```
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```
## **3. Setting Up Python & Miniconda**  

### **3.1. Install Miniconda**  
📌 **Download Miniconda**: [Miniconda Download](https://docs.conda.io/en/latest/miniconda.html)  

📌 **Create and activate an environment for the course:**  
```
conda create -n eo_lab python=3.9
conda activate eo_lab
```

```
pip install geemap earthengine-api jupyterlab geopandas rasterio matplotlib numpy
```
