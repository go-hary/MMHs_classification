# Transit Dashboard: User Guide & Methodology

This guide provides a step-by-step tutorial on how to use the dashboard and explains the scientific methodology used to classify Multimodal Mobility Hubs (MMHs) in Milan.

---

## 1. How to Start: Step-by-Step Tutorial

Follow these steps to explore the transit network and analyze hub performance.

### Step 1: Pick Hub Type
Navigate to the **Control Parameters** panel. Select the primary transit modes you wish to visualize:
* <span style="color:#3182bd; font-weight:bold;">● Train:</span> Regional and suburban backbone linking Milan with the wider metropolitan area.
* <span style="color:#6baed6; font-weight:bold;">● Metro:</span> High-frequency, high-capacity urban network connecting major poles.
* <span style="color:#31a354; font-weight:bold;">● Bus:</span> General bus routes and trolleybus orbital lines.
* <span style="color:#e6550d; font-weight:bold;">● Tram:</span> Dense surface rail grid that distributes flows within the urban fabric.

### Step 2: Pick Hub Statuses
Filter the hubs based on their performance classification. These statuses are derived from the Node/Place framework:
* **Stressed:** High transport supply and high urban intensity.
* **Unbalanced Node:** Strong transport supply but low local activity.
* **Dependency:** Strong local activity but poor transport supply.
* **Balanced:** Equilibrium between transport and urban context.

### Step 3: Change Size and Opacity
Use the sliders in the control panel to customize your view:
* **Size:** Adjust the marker size (e.g., **12px**) to highlight specific nodes.
* **Opacity:** Lower the opacity (e.g., **0.7**) to see overlapping transit lines or underlying map details.

### Step 4: Click on the Graph or the Map
* **The Map:** Click on any square marker to see the station name and its specific metrics.
* **The Scatter Chart:** Click or hover over points in the chart. This graph plots the **Node** value (vertical axis) against the **Place** value (horizontal axis) to identify outliers.

---

## 2. On Each Stop: What You Can See

When you select a hub, the **Station Info** panel displays the following real-time research data:

| Metric | Description |
| :--- | :--- |
| **Number of transport options** | Unique modes available within a 125m walking buffer. |
| **Walking/Transfer time** | Estimated minutes to reach and board at the closest alternative station. |
| **Frequency of arrivals** | Total daily vehicle stops, indicating service reliability. |
| **Routes per stop** | Number of unique destinations accessible without a transfer. |
| **Longest route per stop** | The maximum direct distance reachable from this stop. |
| **BikeMi Distance/Capacity** | Proximity to and bike availability of the nearest shared-mobility station. |
| **Accessibility (PRM)** | Whether the station has facilities for people with reduced mobility. |
| **Weather Protection** | Whether the station provides adequate shelter for users. |
| **Population** | Registered residents living within the specific catchment area. |
| **IAPI Index** | Index of Accessibility by Proximity to daily services. |

---

## 3. Scientific Methodology: The Node/Place Framework

The dashboard implements a revised version of the **Node/Place model**.



### 3.1 ABC Scoring and Catchment
Each hub is scored based on the permanence of its infrastructure (e.g., Train = 6, Metro = 5). These scores determine the **Catchment Area**, which is the radius used to calculate population and services. Larger hubs have a **700m** radius, while smaller nodes use a **165m** radius.

### 3.2 IAPI Index (Place Value)
The **Place** dimension is calculated using the IAPI index, which evaluates proximity to six "baskets" of services:
1. **Public and open spaces**
2. **Commercial activities**
3. **Gathering and cultural spaces**
4. **Sport facilities**
5. **Health and social care**
6. **Education spaces**

---

## 4. Technical Specifications

* **Frontend:** React and Tailwind CSS.
* **Rendering:** Mapbox for geographic data.
* **Typography:** Manrope font family for maximum readability.
* **Application Type:** Standalone Progressive Web App (PWA).
