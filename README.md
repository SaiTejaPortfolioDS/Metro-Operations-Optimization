# 🚇 Delhi Metro Operations Analysis

An end-to-end **data analytics and visualization project** built on the **General Transit Feed Specification (GTFS)** dataset for the **Delhi Metro** network.  
This analysis explores how trips, stops, routes, and time-based intervals interact to reveal operational insights.

---

## 🎯 Project Overview
- **Objective:** Analyze Delhi Metro operations using GTFS feed data to uncover spatial and temporal trends.  
- **Dataset:** GTFS files (`agency.txt`, `routes.txt`, `trips.txt`, `stop_times.txt`, `stops.txt`, `calendar.txt`, `shapes.txt`) containing route, stop, and scheduling information.  
- **Approach:**  
  - Load all GTFS text files into DataFrames.  
  - Perform geospatial visualization and time-series analysis.  
  - Create eight subplots summarizing operational patterns.  
  - Export a final visualization image (`delhi_metro_analysis.png`).  

---

## 🧩 Data Components

| File | Description |
|------|--------------|
| `agency.txt` | Metro agency and operator details |
| `routes.txt` | Route ID, name, and type information |
| `trips.txt` | Defines each trip run for a given route |
| `stop_times.txt` | Arrival/departure times of each trip at each stop |
| `stops.txt` | Stop locations with latitude/longitude |
| `calendar.txt` | Day-of-week schedule flags for service IDs |
| `shapes.txt` | Coordinates representing route geometry |

---

## 🧠 Key Analyses & Visualizations

### 🗺️ 1. Geographical Paths of Delhi Metro Routes
- Plotted route paths using latitude/longitude from `shapes.txt`.
- Color-coded by `shape_id` to differentiate lines.

### 📅 2. Number of Trips per Day of the Week
- Merged `trips.txt` with `calendar.txt` to compute weekly trip frequency.

### 🚉 3. Geographical Distribution of Metro Stops
- Displayed all stop coordinates from `stops.txt` as red dots.

### 🔄 4. Number of Routes per Metro Stop
- Combined `stop_times`, `trips`, and `routes` to calculate how many distinct routes serve each stop.

### ⏰ 5. Average Interval Between Trips by Part of Day
- Computed minute-level gaps between consecutive arrivals at each stop.  
- Grouped into **Morning**, **Afternoon**, and **Evening** to visualize trip regularity.

### 🕓 6. Number of Trips per Time Interval
- Classified times into operational intervals:  
  *Early Morning, Morning Peak, Midday, Evening Peak, Late Evening*.  
- Counted total unique trips within each interval.

### 📊 7. Original vs Adjusted Number of Trips
- Applied adjustment factors (e.g., +20% during peaks) to simulate optimized scheduling.  
- Compared side-by-side bars of original vs adjusted trip counts.

### 📈 8. Final Visualization
- Combined all seven insights into a single figure grid (`2 x 4`) titled  
  **"Delhi Metro Operations Analysis"**.

---

## 📦 Outputs

| File | Description |
|------|--------------|
| `delhi_metro_analysis.png` | Saved multi-plot visualization summarizing the analysis |
| *(Optional)* `.ipynb` / `.py` file | Contains full pipeline code |

---

## ⚙️ How to Run

```bash
# 1. Clone repository
git clone https://github.com/<your-username>/delhi-metro-operations.git
cd delhi-metro-operations

# 2. Install dependencies
pip install pandas matplotlib seaborn

# 3. Upload all GTFS .txt files into the working directory
#    agency.txt, routes.txt, trips.txt, stop_times.txt, stops.txt, calendar.txt, shapes.txt

# 4. Run the script
python delhi_metro_analysis.py
# or open in Jupyter/Colab

# 5. The final figure will be saved and downloaded automatically as:
#    delhi_metro_analysis.png
