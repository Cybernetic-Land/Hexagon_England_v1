# 🌍 BNG Habitat Potential Analysis Tool

A Google Earth Engine (GEE) based tool for analyzing **Biodiversity Net Gain (BNG) Habitat Creation Potential** across England using comprehensive environmental data.

## 📊 Overview

This tool evaluates sites for habitat creation suitability using a **percentage-based scoring model (0-100%)** that combines three key factors:

### Scoring Model

**Formula:** `(Location Points + Soil Points + Water Points) / 18 × 100`

#### 1. 📍 Location Contribution (Max 10 pts, ~55%)
- **Network Enhancement Zone 1:** 10 pts (~55% contribution) - Priority expansion zones
- **Network Enhancement Zone 2 / Fragmentation Action Zone:** 7 pts (~39%) - Buffer/repair zones
- **Restorable Habitat:** 5 pts (~28%) - High restoration potential
- **Network Expansion Zone:** 4 pts (~22%) - Long-term connectivity
- **Background/No Data:** 1 pt (~5%)

#### 2. 🌱 Soil/Feasibility Contribution (Max 5 pts, ~28%)
- **Grade 5 (Very Poor):** 5 pts (+28% boost) - Ideal for habitat
- **Grade 4 (Poor):** 5 pts (+28% boost) - Ideal for habitat
- **Grade 3 (Moderate):** 2 pts (+11%) - Moderate quality
- **Grade 2 / Grade 1:** 0 pts (0%) - Best agricultural land, preserve
- **Non-agricultural / Urban:** 0 pts (0%)

#### 3. 💧 Strategic Water Bonus (Max 3 pts, ~17%)
- **Distance < 50m to Chalk River:** 3 pts (+17% "cherry on top")
- **Distance > 50m:** 0 pts (0%)

### Color-Coded Results

Sites are color-coded from warm (high potential) to cool (low potential):

- 🟣 **Purple (≥83%):** Exceptional - Prime habitat creation sites
- 🔴 **Red (67-83%):** Very High - Excellent opportunity
- 🟠 **Orange (50-67%):** High - Good potential
- 🟡 **Yellow (33-50%):** Moderate - Fair opportunity
- 🟢 **Green (17-33%):** Low - Limited potential
- 🔵 **Blue (0-17%):** Very Low - Minimal suitability

## 🗂️ Data Sources

### Environmental Constraints
- Protected Areas (National Parks, AONBs, etc.)
- Sites of Special Scientific Interest (SSSI)
- Special Areas of Conservation (SAC)
- Special Protection Areas (SPA)
- Ancient Woodland Inventory
- Ramsar Sites
- National Nature Reserves (NNR)

### Opportunity Layers
- **National Habitat Networks Combined:** Network Enhancement Zones, Fragmentation Action Zones, Restorable Habitat
- **Provisional Agricultural Land Classification (ALC):** Grade 1-5 soil quality
- **Chalk Rivers:** Protected chalk stream habitats

## 🚀 Features

- ✅ **Interactive Map:** Click-to-analyze hexagonal grid (H3 resolution 8-10)
- ✅ **Constraint Checking:** Automatic detection of environmental/heritage overlaps
- ✅ **BNG Scoring:** Comprehensive percentage-based habitat potential assessment
- ✅ **Detailed Reports:** Per-hexagon breakdown with explanations
- ✅ **Layer Management:** Toggle visibility of all data layers
- ✅ **Export Ready:** Analysis results available for further processing

## 📦 Requirements

```python
geemap
earthengine-api
h3
ipywidgets
ipyleaflet
```

## 🔧 Setup

1. **Install Dependencies:**
   ```bash
   pip install geemap earthengine-api h3 ipywidgets ipyleaflet
   ```

2. **Authenticate with Google Earth Engine:**
   ```python
   import ee
   ee.Authenticate()
   ee.Initialize(project='your-project-id')
   ```

3. **Run the Notebook:**
   Open `map.ipynb` in Jupyter Notebook or JupyterLab

## 📖 Usage

1. **Draw a Polygon:** Use the drawing tools to define your area of interest
2. **Run Analysis:** Execute the analysis cell to check constraints
3. **View Results:** Hexagons are color-coded by BNG potential percentage
4. **Click for Details:** Click any hexagon for detailed breakdown
5. **Export Data:** Results can be exported for further analysis

## 🎯 Example: Perfect Site

**NEZ1 + Grade 5 Soil + Chalk River = 100% Habitat Potential**
- Location: 10 pts (Network Enhancement Zone 1)
- Soil: 5 pts (Grade 5 - very poor agricultural quality)
- Water: 3 pts (Chalk River within 50m)
- **Total: 18/18 = 100%** ✨

## 📝 License

This project uses data from Natural England and other UK government sources. Please ensure compliance with respective data licenses.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📧 Contact

For questions or collaboration opportunities, please open an issue.

---

**Note:** This tool is for preliminary assessment only. Detailed ecological surveys and professional consultation are required for actual habitat creation projects.

