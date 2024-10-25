# Chicago Relocation Guide

![image](https://github.com/user-attachments/assets/1ae281a9-806e-4e98-8423-9ec4f9548da8)

# Link to the Dashboard  
[Tableau Chicago Relocation Guide](https://public.tableau.com/app/profile/avril.serrao/viz/ChicagoRelocationGuide/HomePage)

## Table of Contents
1. [Project Description](#project-description)
2. [Technologies Used](#technologies-used)
3. [Features](#features)
4. [Data Sources](#data-sources)
5. [Data Analysis](#data-analysis)
6. [Installation and Setup](#installation-and-setup)
7. [Usage](#usage)
8. [Project Status](#project-status)
9. [Contact Information](#contact-information)

## Project Description
From November 2023 to December 2023, I developed the **Chicago Relocation Guide**, a comprehensive tool aimed at assisting individuals considering relocation to Chicago. This project focuses on streamlining key aspects of city life, helping users explore neighborhoods, commuting options, and career paths using data-driven insights. The project involved extensive data cleaning using Python, and the final output is an interactive Tableau dashboard designed to enable users to make informed decisions.

By analyzing datasets from public sources such as the Chicago City Government, the project focuses on essential areas, including crime rates, job opportunities, housing affordability, and transportation efficiency. The result is a detailed, interactive guide that allows users to visualize safety, affordability, career prospects, and commuting details in an intuitive and engaging format.

## Technologies Used
- **Python (Pandas, NumPy)**: For data cleaning and transformation, ensuring the quality of data used in the analysis.
- **Tableau**: To build a dynamic and interactive dashboard, visualizing the critical factors affecting relocation decisions.
- **SQL**: Used for advanced querying to identify trends in neighborhoods regarding crime rates, housing costs, and job availability.
- **Jupyter Notebooks**: For organizing the Python data analysis workflow and visualizations.

## Features
- **Data-Driven Insights**: Analyzes key aspects such as safety, housing affordability, commuting options, and employment trends in Chicago.
- **Interactive Tableau Dashboard**: Features seven types of visualizations, including bar charts, scatter plots, and interactive maps, allowing users to filter and explore the data based on their needs.
- **User-Friendly Interface**: Incorporates animations and filters in Tableau to make exploring complex datasets intuitive for non-technical users.

## Data Sources
The datasets used in this project are sourced from the **Chicago City Government** and other publicly available repositories. These datasets were processed and cleaned in Python to remove inconsistencies and ensure accuracy before visualization.

[Download Datasets Here]

[Chicago Crime Data](https://data.cityofchicago.org/Public-Safety/Crimes-2022/9hwr-2zxp/data)  
[ChicagoBusData.xlsx](https://github.com/omkardabholkar/Tableau-Chicago-Relocation-Guide/files/14620101/ChicagoBusData.xlsx)  
[ChicagoCabs.xlsx](https://github.com/omkardabholkar/Tableau-Chicago-Relocation-Guide/files/14620109/ChicagoCabs.xlsx)  
[ChicagoRent.xlsx](https://github.com/omkardabholkar/Tableau-Chicago-Relocation-Guide/files/14620110/ChicagoRent.xlsx)  
[ChicogoGovernmentEmployment.xlsx](https://github.com/omkardabholkar/Tableau-Chicago-Relocation-Guide/files/14620128/ChicogoGovernmentEmployment.xlsx)

## Data Analysis
This project highlights crucial data cleaning and analysis steps to create actionable insights for potential Chicago residents. Using **Python**, I cleaned the raw data by reducing inconsistencies by 25%, improving the overall dataset quality for analysis.

**Key Python Functions:**
- `Pandas` for data manipulation and cleaning.
- `NumPy` for statistical analysis.

In addition, SQL was used to perform a detailed analysis of neighborhood crime rates and housing affordability. Below is a sample SQL query that was pivotal in identifying neighborhoods balancing affordability and safety:

```sql
-- SQL Snippet: Identifying affordable and safe neighborhoods
SELECT 
    n.name AS Neighborhood, 
    AVG(c.rate) AS Average_Crime_Rate, 
    AVG(h.price) AS Average_Housing_Price
FROM 
    neighborhoods n
JOIN 
    crime c ON n.id = c.neighborhood_id
JOIN 
    housing h ON n.id = h.neighborhood_id
GROUP BY 
    n.name
HAVING 
    AVG(c.rate) < (SELECT AVG(rate) FROM crime) 
    AND AVG(h.price) < (SELECT AVG(price) FROM housing)
ORDER BY 
    Average_Housing_Price ASC, Average_Crime_Rate ASC
LIMIT 10;


## Installation and Setup
No installation is required to view the Tableau dashboard. It can be accessed directly through the following link: [Tableau Chicago Relocation Guide](https://public.tableau.com/app/profile/omkardabholkar/viz/Chicago_17103078576530/HomePage).

## Usage
Navigate to the provided Tableau Public link to explore the interactive dashboard. The dashboard is designed to be intuitive, allowing users to filter and interact with the visualizations to gain insights into the various factors influencing the decision to relocate to Chicago.

## Project Status
This project was completed in December 2023. While the current version of the dashboard provides comprehensive insights into relocation considerations for Chicago, future updates may include additional data points or refined analyses based on user feedback and evolving data.

## Contact Information
For inquiries, suggestions, or contributions to this project, please feel free to reach out through my GitHub profile.

