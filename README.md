# Transit Dashboard & MMH Research Guide

This dashboard is an interactive platform designed to visualize and analyze **Multimodal Mobility Hubs (MMHs)** within the Milan Metropolitan Area. Built with **React** and **Tailwind CSS**, it utilizes the **Manrope** font family for a professional, data-centric interface.

---

## 1. Research Methodology: The Node/Place Framework

The application implements the **Node/Place model**, which evaluates a station's performance by balancing its transport accessibility (**Node**) with the intensity of its urban surroundings (**Place**).

### 1.1 Spatial Identification & ABC Scoring
Potential MMHs are identified where multiple transit nodes are located in proximity to one another. The methodology uses a re-adapted **ABC Location Policy** to score hubs based on the permanence of their transport infrastructure:

| Transport Type | Location Type | Initial Score |
| :--- | :--- | :--- |
| **Train** | A | 6 |
| **Metro** | A | 5 |
| **Tram** | A | 4 |
| **Bus** | A | 3 |
| **Regional Bus** | A | 2 |
| **P+R (Interchange Parking)** | B | 1 |

> **Hub Score ($H_s$):** The final score is calculated as $H_s = S + I_h$.
> * **S** = Sum of initial scores of all unique transport types within a 125m buffer.
> * **$I_h$** = Initial score of the hub itself.

### 1.2 Catchment Area Assignment
To accurately reflect the urban role of a station, the dashboard assigns variable catchment radii based on the **Hub Score**. Larger, high-capacity hubs (like Central Train Stations) are analyzed with a 700m radius, while smaller local bus nodes use a 165m radius.

---

## 2. Dashboard Interface & Navigation

The dashboard provides a geographic overview and deep-dive analytics for the transit network.

### 2.1 The Interactive Map
* **Color-Coded Hubs**: Markers are categorized by mode: Train (Blue), Metro (Light Blue), Bus (Green), and Tram (Orange).
* **Real-time Selection**: Clicking a marker updates the **Station Info** panel with that specific station's name and metrics.
* **Scatter Chart**: Located in the sidebar, this graph plots nodes based on their **Node** and **Place** z-scores to identify "Balanced," "Stressed," or "Unbalanced" hubs.

### 2.2 Control Parameters
The right-hand sidebar allows you to customize the data visualization:
* **Hub Status Filtering**: Toggle visibility for specific classifications like **Stressed**, **Dependency**, or **Balanced**.
* **Visual Controls**: Use the **Size** and **Opacity** sliders to adjust marker visibility against the dark map theme.

---

## 3. Data Indicators & Definitions

The **Station Info** panel presents standardized indicators derived from GTFS data and urban research.

### Node Dimension (Transport)
* **$N_1$ (Multiple Modes)**: The number of unique transport options within a 125m buffer.
* **$N_2$ (Transfer)**: Walking and total transfer time to the closest alternative station.
* **$N_3$ (Supply)**: Frequency of arrivals (stops/day) and the number of direct destinations accessible.
* **$N_4$ (Shared Mobility)**: Distance to and capacity of the nearest **BikeMi** station.
* **$N_5$ (Physical Conditions)**: Presence of elevators/ramps and weather protection.

### Place Dimension (Urban Context)
* **$P_1$ (Population)**: Number of registered residents within the calculated catchment area.
* **$P_2$ (IAPI Index)**: The **Inclusive Accessibility by Proximity Index**, evaluating reachable daily services (education, health, commerce) within a 15-minute walk.

---

### Technical Note
This application is optimized as a **Standalone Progressive Web App**. You can "Install" the dashboard from your browser to remove the address bar and use it as a native desktop or mobile application.
