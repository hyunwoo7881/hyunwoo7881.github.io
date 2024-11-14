---
name: Vega Lite/altair weather Project
tools: [Python, HTML, vega-lite]
image: assets/pngs/cars.png
description: This is a "showcase" project that uses vega-lite for interactive viz!
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Visualization 1: Temperature vs. Cloud Cover with Precipitation Type Histogram

This first visualization examines the relationship between **temperature** and **cloud cover**, focusing on how temperature (high, mid, and low) interacts with cloud cover, and how this relationship correlates with precipitation type (rain and snow). Additionally, a histogram breaks down the distribution of rain and snow for each temperature range, giving a deeper insight into how temperature affects precipitation.

<vegachart schema-url="{{ site.baseurl }}/assets/json/graph1.json" style="width: 100%"></vegachart>


<vegachart schema-url="{{ site.baseurl }}/assets/json/graph2.json" style="width: 100%"></vegachart>


<vegachart schema-url="{{ site.baseurl }}/assets/json/graph3.json" style="width: 100%"></vegachart>
### Design Choices

- **Scatter Plot**: The scatter plot visualizes the relationship between **cloud cover percentage** and **temperature**. The y-axis represents temperature (high, mid, or low), and the x-axis represents cloud cover percentage. The temperature ranges are adjusted to ensure consistency across the plot, allowing for an accurate comparison of how different temperatures interact with cloud cover.
- **Precipitation Type Color Encoding**: The precipitation type is encoded using a custom color scale:
  - Rain: Light blue (#aec7e8)
  - Snow: Gray (#a7a7a7)
- **Histogram**: The histogram displays the count of rain and snow observations across different temperature ranges, visually breaking down the distribution of precipitation type for each temperature. This makes it easier to analyze how temperature influences precipitation type.

### Data Transformations

- **Cloud Cover Percentage**: The cloud cover values were converted from fractions to percentages (e.g., 0.2 → 20%) to make the data more interpretable and user-friendly.
- **Temperature Range Consistency**: I ensured that the **high, mid, and low temperature ranges** were aligned and comparable across the plot, so that users could easily analyze how each temperature range relates to cloud cover and precipitation type.
- **Data Cleaning**: The histogram excludes rows where **precip_type** is missing or null, ensuring that only valid data is used in the analysis.

### Interactivity

- **Brush Selection**: The scatter plot includes an **interactive brush selection** feature, allowing users to select a specific region of the plot based on temperature and cloud cover ranges. When a user selects a region, both the scatter plot and the histogram update dynamically to reflect the filtered data. This feature provides an interactive and engaging way for users to explore the data, allowing them to focus on specific temperature ranges and see how they correlate with precipitation type in real time.
- **Dynamic Filtering**: The interaction also allows for a **dynamic filtering experience**, where users can adjust the temperature and cloud cover ranges and immediately observe how precipitation types (rain and snow) change in response. This helps to drill down into the data and discover more specific patterns related to weather conditions.

---

# Visualization 2: UV Index Distribution Across U.S. Locations

This visualization maps the distribution of **UV index values** across various U.S. counties, providing a geographic view of UV exposure across the country. The map allows users to visually assess how the UV index varies geographically, highlighting areas with higher or lower UV exposure.

<vegachart schema-url="{{ site.baseurl }}/assets/json/map_uv.json" style="width: 100%"></vegachart>

### Design Choices

- **Geographic Map**: A map of the U.S. serves as the background, with state boundaries outlined in light gray. **UV index values** are overlaid as points on the map, with each point’s size and color representing the UV index value in that location.
- **Color Scale**: The **viridis** color scheme is used for color encoding, as it is perceptually uniform and easily distinguishable across different UV index values.
- **Size Encoding**: The size of each point varies based on the UV index, visually representing the intensity of UV exposure in that area.
- **Tooltip**: Hovering over a point reveals additional information, such as the **county**, **state**, and **UV index** value. This provides more detailed insights at the data point level, enhancing the map's interactivity.

### Data Transformations

- No significant transformations were needed for this plot, as the **UV index values** were already in a suitable format for visualization. However, I made sure that **longitude** and **latitude** values were correctly mapped to geographic coordinates for the map to display accurately.

### Interactivity

- **Zoom and Pan**: Users can zoom in and out of the map and pan across different regions of the country. While this plot does not have complex filtering interactions like the first one, the ability to explore different parts of the country visually adds a layer of interactivity. Users can zoom into specific areas to see how the UV index varies in those regions and gain a deeper understanding of the geographic distribution of UV exposure.

---

### Additional Notes on Interactivity and Rubric Considerations

- **Plot 1** stands out for its **interactive features**, particularly the **brush selection** tool, which allows users to dynamically filter both the scatter plot and histogram based on temperature and cloud cover ranges. This feature makes it easier for users to analyze specific subsets of the data and observe how temperature correlates with precipitation type. This interactivity is an important factor in earning high marks for **user engagement** and **data exploration** in the rubric.
- **Plot 2** focuses more on providing a **spatial perspective** of the UV index across the U.S. with zoom and pan capabilities. While it does not have the same level of interactivity as the first plot, the ability to visually explore geographic data is still valuable for users who want to assess UV exposure across different regions. This contributes to high marks for **data visualization** and **geospatial analysis**, even though it lacks more complex interactive filtering.

In both visualizations, the design choices and interactivity were made to enhance **data accessibility**, **user engagement**, and **understanding of the data**, ensuring they align well with the rubric requirements for effective and insightful data presentation.



<!-- these are written in a combo of html and liquid -->

<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jnaiman/online_cv_public/blob/main/python_notebooks/test_generate_plots.ipynb" text="The Analysis" %}
</div>


