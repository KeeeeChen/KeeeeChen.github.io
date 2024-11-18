
---
title: "Building Usage Analysis"
layout: post
---

# Building Usage Analysis

This post presents an analysis of building usage patterns and their statuses using two visualizations. The data is sourced from a public repository, and the analysis was conducted in a Python notebook.

## Visualization 1: Building Usage Distribution
This visualization is a pie chart depicting the distribution of building usage types. Each segment of the pie chart represents a specific usage description, such as "Storage," "Industrial," or "Residential," with the size of the segment proportional to the number of buildings in that category. This visualization provides an overview of how buildings are predominantly used, emphasizing the most and least common usage types.

**Design Choices**: 
- A **pie chart** was chosen to provide an intuitive sense of proportion. 
- The **theta encoding** is mapped to the count of buildings, while **color encoding** differentiates usage categories using a categorical palette. This color scheme ensures each category is visually distinct, enhancing readability.
- A **tooltip** was added to display the usage description and count dynamically when hovering over each segment.

**Data Transformations**:
- The raw dataset contained missing values in the "Usage Description" column, which were replaced with "Unknown" to avoid data loss.
- A frequency table was generated to compute the counts for each usage type, serving as input for the visualization.

<div id="viz1"></div>

## Visualization 2: Relationship between Building Usage and Status (Interactive)
This interactive bar chart explores the relationship between building usage types and their current statuses (e.g., "In Use," "Abandon"). Users can select a specific building usage type from a dropdown menu to dynamically filter and display the status distribution for that category, enabling a focused analysis.

**Design Choices**:
- A **bar chart** was chosen for its ability to represent comparative quantities effectively.
- **Color encoding** is used to represent building statuses, providing a clear distinction between categories. The colors were selected from a categorical palette for consistency and clarity.
- An interactive **dropdown menu** allows users to select a building usage type, dynamically filtering the chart to display only the relevant statuses.

**Data Transformations**:
- Missing values in the "Bldg Status" column were filled with "Unknown" to maintain data completeness.
- The data was grouped by "Usage Description" and "Bldg Status," with counts calculated for each combination. This grouping enabled the creation of a detailed dataset for visualization.
- The filtered dataset is updated dynamically based on user interaction with the dropdown menu, ensuring an engaging and focused user experience.

**Interactivity**:
- The dropdown menu interactivity enhances the visualization's clarity by allowing users to isolate specific building usage types. This functionality facilitates a deeper understanding of the data by enabling targeted exploration, which would not be as straightforward in a static chart.

<div id="viz2"></div>

## Resources
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_data/blob/main/building_inventory.csv" text="The Data" %}
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_data/blob/main/Workbook.ipynb" text="The Analysis" %}
