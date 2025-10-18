# Tower-Hamlets-Schools-and-Infrastructure-Data-Science-Project


# Tower Hamlets Education & Culture Explorer

An interactive data project that maps **schools** and **cultural infrastructure** (libraries, museums, theatres, cinemas, maker spaces, etc.) across the London Borough of **Tower Hamlets**. It brings together multiple open datasets, adds simple geospatial modelling (nearest–neighbour lookups and K‑Means clustering), and packages the insights into a lightweight Streamlit app.

> 💡 **Goal**: help residents, students, and families explore the local education landscape and nearby cultural resources at a glance.

---

## 🎯 What this project does

- **Maps schools in Tower Hamlets** (from the London Schools Atlas) with metadata such as phase and gender intake.
- **Joins Ofsted ratings** to schools so you can filter by quality.
- **Plots 20+ categories of cultural infrastructure** (e.g., Libraries, Museums & Galleries, Cinemas, Theatres, Music Venues, Creative Workspaces, Makerspaces, Fashion/Jewellery/Textiles, LGBT venues, etc.).
- **Finds the closest cultural spots** to a selected school (simple Euclidean distance over lat/lon).
- **Clusters cultural points** using **K‑Means** to reveal “epicentres” by category (cluster count is configurable).
- **Overlays ward boundaries** for geographic context.
- Ships with a **notebook** for exploration and a **Streamlit app** (optional) for quick sharing.

---

## 🧰 Tech stack

- **Python**: `pandas`, `numpy`, `geopandas`, `folium`, `scikit‑learn`, `fastkml`
- **Visualization / UI**: `folium` maps, **Streamlit** app
- **Geo**: ward `.geojson` layers, point datasets (schools & cultural venues)

---

## 🔎 Methods (at a glance)

- **Data cleaning & joins**  
  - Filter schools: `LA_NAME == "Tower Hamlets"`; select useful columns (name, phase, URN, ward, coordinates).  
  - Join **Ofsted** ratings on `URN`/name where available.
- **Nearest cultural venues**  
  - For a selected school, compute straight‑line (Euclidean) distance to each venue and return the top *n*. (*Note:* this is a simple proxy; great‑circle distance or network routing would be more realistic.)
- **K‑Means clustering**  
  - Cluster cultural points to reveal dense “epicentres”. The number of clusters *k* is user‑tunable.
- **Geo layers**  
  - Ward boundaries loaded from `.geojson` files; displayed in **Folium** with layer controls.

---

## 📊 What I learned / built

- Working with **geospatial data** in Python (GeoPandas, Folium, GeoJSON).
- Building a **simple geospatial model** (nearest neighbour, K‑Means) for exploratory insight.
- Wrapping a notebook into a **shareable Streamlit app**.

