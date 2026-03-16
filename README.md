# Connecticut Real Estate Sales Dashboard

An interactive data dashboard analyzing 20+ years of Connecticut real estate transactions (2001–2022) using Python, Panel, and Plotly. Built as a project for DS3500 (Advanced Programming in Data Science) at Northeastern University.

## Overview

This dashboard enables users to explore Connecticut real estate sales data through three interactive views — a Sankey diagram, a geographic map, and a filterable data table. Users can filter by year, town, property type, and sale price range to uncover pricing trends, regional patterns, and property type distributions across the state.

As part of the assignment, we also compared our custom-built dashboard against an AI-generated version (built using Claude) to evaluate differences in insight generation and design choices.

## Dashboard Features

**Sankey Diagram** — Visualizes the flow of sales from towns to residential property types, revealing which towns have the most activity in each housing category.

**Interactive Map** — Scatter map of sale locations plotted using parsed geospatial coordinates (WKT POINT → lat/lon), with hover details for each transaction.

**Filterable Table** — Paginated tabular view of all transactions matching the current filters.

**Dynamic Filters** — Year selector, multi-select for towns and property types, a price range slider that updates dynamically per year, and a reset button to restore defaults.

## Key Insights

- Densely populated areas of Connecticut showed significantly more sales activity (visible on the map)
- New Haven had the most three-family housing sales compared to other towns (visible in the Sankey)
- Single-family homes dominate the market at ~37% of all sales, followed by unknown/unclassified types (~35%)
- Median sale prices rose from ~$90K (2001) to ~$350K (2022), with a notable dip during 2008–2012 reflecting the housing crisis
- Pre-2006 data lacks residential type classifications, appearing as "Unknown" in the dashboard

## Data Source

[Connecticut Real Estate Sales 2001–2022](https://www.kaggle.com/datasets/omniamahmoudsaeed/real-estate-sales-2001-2022) — sourced from Kaggle, originally from Connecticut's Office of Policy and Management.

## Tech Stack

- **Python** — Core language
- **Panel** — Dashboard framework and interactive layout
- **Plotly** — Sankey diagram (`plotly.graph_objects`) and scatter map (`plotly.express`)
- **Pandas** — Data cleaning, filtering, and aggregation
- **Tabulator** — Paginated data table widget

## How to Run

1. Install dependencies:
   ```
   pip install panel pandas plotly bokeh
   ```
2. Place `Real_Estate_Sales_2001-2022_GL.csv` in the same directory as the script
3. Run:
   ```
   python real_estate_dashboard.py
   ```
4. Dashboard opens at `http://localhost:5006`

## My Contributions

- **Data pipeline** — Co-built `RealEstateAPI.load_data()` and `filter_data()` for CSV ingestion, geospatial coordinate parsing (WKT → lat/lon), and multi-filter support
- **Sankey diagram** — Designed and implemented `make_sankey()` to aggregate Town → Residential Type flows using Plotly's Sankey API
- **Dynamic slider** — Co-developed `_update_sale_slider()` for year-responsive price range filtering
- **AI dashboard comparison** — Led the analysis section of the poster comparing our custom dashboard against the AI-generated version, including key insights
- **Poster** — Completed the AI Dashboard section and comparative insights

## Collaborators

Built for DS3500 at Northeastern University (May 2025).

- **Rianna Wadhwani** — Data pipeline, Sankey visualization, AI dashboard analysis, poster insights
- **Rishi Urs** — Data pipeline, Map visualization, Table view, Reset Filters button, poster dashboard section
