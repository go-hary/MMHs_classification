# Transit Dashboard: User Guide & Methodology

This guide provides a step-by-step tutorial on how to use the dashboard and explains the underlying scientific methodology used to classify Multimodal Mobility Hubs (MMHs) in Milan.

---

## 1. How to Start: Step-by-Step Tutorial

Follow these steps to explore the transit network and analyze hub performance.

### Step 1: Pick Hub Type
Navigate to the **Control Parameters** panel in the top right. Select the primary transit modes you wish to visualize:
* **Train**: Regional and suburban backbone.
* **Metro**: High-frequency urban network.
* **Bus**: General and trolleybus lines.
* **Tram**: Dense surface rail grid.

### Step 2: Pick Hub Statuses
Filter the hubs based on their performance classification. These statuses are derived from the Node/Place framework:
* **Stressed**: High transport supply and high urban intensity.
* **Unbalanced Node**: Strong transport supply but low local activity.
* **Dependency**: Strong local activity but poor transport supply.
* **Balanced**: Equilibrium between transport and urban context.

### Step 3: Change Size and Opacity
Use the sliders in the control panel to customize your view:
* **Size**: Adjust the marker size (12px by default) to highlight specific nodes.
* **Opacity**: Lower the opacity (0.7 by default) to see overlapping transit lines or underlying map details.

### Step 4: Interact with the Map or Graph
* **The Map**: Click on any square marker to see the station name and its specific metrics.
* **The Scatter Chart**: Click or hover over points in the chart. This graph plots the **Node** value (vertical axis) against the **Place** value (horizontal axis) to help you find outliers in the network.

---

## 2. What You See: Station Info & Metrics

When you click on a hub, the **Station Info** panel displays the following real-time research data:

| Metric | Description |
| :--- | :--- |
| **Transport options within 125m** | The number of unique transit types available within a 2-minute walk. |
| **Walking/Transfer Time** | The estimated time in minutes to reach and board at the closest alternative station. |
| **Frequency of Arrivals** | Total daily vehicle stops, indicating service reliability and capacity. |
| **Routes per Stop** | The number of unique destinations accessible without a transfer. |
| **Longest Route per Stop** | The maximum direct distance reachable from this stop. |
| **BikeMi Distance/Capacity** | Proximity to and bike availability of the nearest shared-mobility station. |
| **Accessibility (PRM)** | Whether the station has elevators, ramps, or escalators for limited mobility. |
| **Weather Protection** | Whether the station provides adequate shelter from environmental factors. |
| **Population** | Number of registered residents living within the hub's specific catchment area. |
| **IAPI Index** | The Inclusive Accessibility by Proximity Index, measuring access to daily services. |

---

## 3. Scientific Methodology: The Node/Place Framework

The dashboard operates on a revised version of the **Bertolini Node/Place model**.



### 3.1 ABC Scoring and Catchment
Each hub is scored based on the permanence of its infrastructure (Train = 6, Metro = 5, etc.). These scores determine the **Catchment Area**, which is the radius used to calculate population and services. Larger hubs have a 700m radius, while smaller nodes use a 165m radius.

### 3.2 IAPI Index (Place Value)
The **Place** dimension is calculated using the IAPI index, which evaluates proximity to six "baskets" of services:
1. Public and open spaces.
2. Commercial activities.
3. Gathering and cultural spaces.
4. Sport facilities.
5. Health and social care.
6. Education spaces.

---

## 4. Technical Specifications

* **Frontend**: React and Tailwind CSS.
* **Rendering**: Mapbox for geographic data.
* **Typography**: Manrope font family for readability.
* **Application Type**: Standalone Progressive Web App (PWA).
