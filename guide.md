# Dashboard Features & Interface Guide

This guide details the interactive components of the **Transit Dashboard** and how they relate to the underlying MMH research methodology.

---

## 1. Global Navigation & Map
The main interface consists of a dynamic Mapbox-powered environment that serves as the primary canvas for transit analysis.

* **Interactivity**: You can pan, zoom, and click on individual transit hubs to retrieve localized data.
* **Hub Visualization**: Hubs are represented by square markers, with colors corresponding to the primary transit mode:
    * **Blue**: Train nodes.
    * **Light Blue**: Metro nodes.
    * **Green**: Bus nodes.
    * **Orange**: Tram nodes.

---

## 2. Control Parameters Panel
Located at the top right, this panel allows you to filter and customize the data displayed on the map.

### Hub Filters
* **Hub Type**: Toggle individual transit modes (Train, Metro, Bus, Tram) on or off to focus your analysis.
* **Hub Status**: Filter hubs based on their Node/Place classification:
    * **Stressed**: High demand on both transport and urban services.
    * **Unbalanced Node**: Strong transport supply but low urban density/services.
    * **Dependency**: Strong urban density but poor transport connectivity.
    * **Balanced**: Equilibrium between transport supply and urban services.

### Visual Customization
* **Size Slider**: Dynamically adjust the scale of the map markers (from 1px to 20px).
* **Opacity Slider**: Change the transparency of markers to better see the underlying street network or overlapping hubs.

---

## 3. Scatter Chart Analytics
The **Scatter Chart** provides a mathematical visualization of the entire network's performance.

* **X-Axis (Place)**: Represents the normalized urban intensity and service diversity.
* **Y-Axis (Node)**: Represents the normalized transport accessibility and frequency.
* **Function**: This chart allows you to instantly see which hubs are "outliers" (e.g., a hub very high on the Y-axis but low on the X-axis is an "Unbalanced Node").



---

## 4. Station Info (Deep-Dive Panel)
When a hub is selected, this panel displays the specific z-scores and raw metrics used in the MMH classification.

| Feature | Description |
| :--- | :--- |
| **Transport Options** | Number of unique transit types within a 125m walking buffer. |
| **Transfer Time** | Estimated minutes required to walk and wait for a connection at the nearest alternative station. |
| **Frequency of Arrivals** | Total number of daily vehicle stops (frequency) at that specific hub. |
| **BikeMi Proximity** | Distance (meters) and bike capacity of the nearest shared-mobility station. |
| **Accessibility (PRM)** | Binary indicator (Yes/No) for ramps, elevators, and facilities for people with reduced mobility. |
| **IAPI Index** | The proximity score for daily services (Schools, Health, Culture, etc.). |

---

## 5. Technical Specifications
* **Responsive Layout**: The dashboard uses a flexible sidebar system that collapses on smaller screens.
* **Performance**: Built with **React** to ensure that filtering thousands of transit nodes happens in real-time without page refreshes.
* **Offline Ready**: As a Progressive Web App (PWA), the dashboard can be cached for faster loading on subsequent visits.
