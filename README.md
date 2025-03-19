

# Analytical Power BI Dashboard Project

## Overview

This project is an advanced Analytical Power BI Dashboard, designed to showcase a variety of Business Intelligence (BI) concepts and techniques. It implements data modeling for efficient data availability and accessibility, uses Power Query for advanced-level data manipulation and transformation, and utilizes DAX (Data Analysis Expressions) for deriving quantitative insights.

## About the Data & Transformation

The dataset for this project was obtained from an open-source platform and consists of multiple dimension tables and a fact table. The raw data was loaded directly into Power BI, where necessary data transformations were performed using Power Query. Additionally, extra data was incorporated, such as URLs for each nation's flag, to enhance the visualization experience.

To ensure efficient data management, a star schema model was developed, comprising:

- 4 Dimension Tables:

  - Drivers

  - Constructors

  - Circuits

  - Races

- 1 Fact Table: Contains detailed quantitative information about each race.

Logical relationships were established between all tables, and the data model ensures seamless querying and analysis. The data model diagram is available within the repository for reference.

![star](https://github.com/Vruditdp/F1-Dashboard-Power-BI/assets/55894200/7196ca9f-efd9-4b15-b1e1-91af2dfeec90)

## Dashboard & Pages

The primary goal of this dashboard is to facilitate analysis of a large historical dataset in an intuitive and interactive manner. Due to the dataset's size and complexity, multiple pages were developed, featuring visually appealing graphics and appropriate chart selections.

1. Landing Page

- Displays general details such as:

  * Top Driver

  - Total Teams

  - Total Drivers

  - Total Races

- A Year Filter is provided for selecting specific timeframes.

- A Navigation Button is included, leading to the Navigation Page.

2. Navigation Page

- This page offers three options:

  - Circuit Analysis

  - Driver Performance

  - Constructor Performance

3. Circuit Analysis Page

- Features a world map displaying different circuit locations across the globe.

- A detailed table lists information for each circuit.

- Hovering over any table cell reveals additional details about the circuit.

4. Driver Performance Page

- Displays the top drivers based on their points.

- Provides winner information for each Grand Prix.

5. Constructor Performance Page

- Highlights top constructors based on race wins.

- Analyzes winning constructors for each Grand Prix.

- A matrix table is included to show the number of wins per constructor across different Grand Prix events.

6. Python-Enhanced Visualization Page

- A Pie Chart visualizing the nationality of each constructor, filtered by the selected timeframe.

- This chart was developed using Python, demonstrating how Power BI supports Python integration for complex data visualizations.

## DAX Formulas

Several DAX calculations were implemented to derive meaningful insights from the dataset. Below are some key formulas used in the dashboard:

1. Total Number of Races

No_of_Races = DISTINCTCOUNT('aly6060 fact_result'[raceId])

2. Top Driver Points

TopDriverPoints = CALCULATE(MAX('aly6060 fact_result'[points]),\
      ALL('aly6060 fact_result'), \
      VALUES('aly6060 fact_result'[Driver's Name]))

3. Top Performing Driver

TopDriverName =
CALCULATE(
    MAX('aly6060 fact_result'[Driver's Name]),
    FILTER(
        'aly6060 fact_result',
        'aly6060 fact_result'[points] = [TopDriverPoints]
    )
)

4. Total Number of Cities

Total Cities = DISTINCTCOUNT('aly6060 fact_result'[aly6060.dim_circuits.location])

5. Total Number of Wins

WinCount = COUNTROWS(FILTER('aly6060 fact_result', 'aly6060 fact_result'[Win]= "Yes"))

Many additional DAX measures were created to further enhance data analysis and visualization.

## Conclusion

This Power BI Dashboard effectively combines creative data visualization with advanced data analytics. It provides an intuitive interface to explore vast historical racing data, uncover trends, and derive meaningful business insights. The integration of Power BI's DAX calculations and Python-based visualizations showcases the powerful capabilities of modern data analytics tools.

Feel free to explore the dashboard and analyze the insights it provides!

### Repository Contents

- Power BI .pbix File: Contains the complete dashboard. ![download here](pb1.pbix)


- Dataset Files: Raw and transformed data.


- Python Notebook Scripts: For custom visualizations.

- Documentation: Detailed explanation of data sources, transformations, and modeling techniques.






<!-- The link for the Power BI dashboard is: -->
<!-- https://app.powerbi.com/view?r=eyJrIjoiMDljYjdjNjEtM2MxZi00NzhmLWI1MzktODIzZmE4YTg5NWJjIiwidCI6ImE4ZWVjMjgxLWFhYTMtNGRhZS1hYzliLTlhMzk4YjkyMTVlNyIsImMiOjN9  -->


