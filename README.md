# MARIA - Mapping and Analysis of Risks and Insights on Abuse Against Women

**Welcome to the MARIA Project!**  
This repository contains all the information needed to reproduce our research, which is dedicated to extracting, transforming, and analyzing data on domestic violence in Brazil obtained from the **Women’s Service Center (Call 180)**. The project also features [interactive dashboards](https://public.tableau.com/app/profile/isabel.manssour4994/viz/MARIAEnglish/Incio) created with Tableau Public to visualize trends, patterns, and insights related to this critical issue. 

---

## 📋 Project Overview

MARIA (**Mapping and Analysis of Risks and Insights on Abuse Against Women**) is a comprehensive ETL (Extract, Transform, Load) pipeline designed to process, analyze, and enrich public data on domestic violence. The goal is to provide a clear understanding of the dynamics of abuse against women, supporting informed decision-making, awareness campaigns, and public policy development.

### Data Sources
1. **Call 180**: Open data provided by Brazil's Ministry of Human Rights and Citizenship.  
   - Period: 2014–2024 (excluding the 2019 balance sheet file containing consolidated summary data).
   - Format: `.csv` files categorized by year/semester.
2. **2022 Census Data**: Used for demographic analysis, including population size, education levels, race, and regional distribution.

---

## ⚙️ Features

### 1. ETL Pipeline
The data processing pipeline, implemented in Python, is divided into three main stages:  
- **Stage 1: Data Standardization**  
  - Normalizing column names and formatting values (uppercase, no accents).  
  - Filtering records specific to domestic violence.  
  - Removing duplicates from data files post-2020.

- **Stage 2: Dataset Integration and Cleaning**  
  - Merging datasets into four distinct groups based on changes in data collection formats:  
    - 2014 to November 2018.  
    - December 2018 to the end of 2019.  
    - First half of 2020.  
    - Second half of 2020 to 2023.  
  - Standardizing names of countries, cities, and professions.

- **Stage 3: Unified Dataset Creation**  
  - Combining all cleaned datasets into a single, consistent dataset.  
  - Adding a "Categories" column to classify violations based on the [**Maria da Penha Law**](https://tinyurl.com/2sz9cfsa):  
    - Physical Violence  
    - Psychological Violence  
    - Sexual Violence  
    - Moral Violence  
    - Patrimonial Violence  

Scripts also allow seamless updates whenever new data is released.

---

### 2. Interactive Dashboards
- Built with **Tableau Public**, the dashboards visualize trends in domestic violence cases over time and across regions.  
- Access the dashboard here: [MARIA Dashboard](https://public.tableau.com/app/profile/isabel.manssour4994/viz/MARIAEnglish/Incio).

---

### 3. Clustering Analysis
- Experimental clustering techniques:
- **K-means** and **K-modes** were applied to identify patterns and groupings within the data.  
- This exploration aims to provide deeper insights into recurring trends and anomalies in the dataset.

---

### 4. Data Translation
- To reach a broader audience, data translation scripts (Python-based) convert the dataset and its outputs into English.  
- This initiative supports global collaboration and awareness of domestic violence issues in Brazil.

---

## 📁 Repository Structure

```plaintext
MARIA/
├── Clusterização/             # Clustering analysis using K-means and K-modes.
├── Tradução/                  # Scripts and outputs for translating data into English.
├── Tratamento/                # ETL pipeline scripts (Stages 1, 2, and 3 described above).
├── README.md                  # Project overview and details (this file).


## Citation

Please refer to this work by citing the paper indicated below.

Eduarda Patricio, Gabriel Zurawski, André Rollwagen, Isabel Manssour. 
Explorando Dados Governamentais para Prevenção da Violência de Gênero: Uma Abordagem Visual. 
In Anais do XII Workshop de Computação Aplicada em Governo Eletrônico, 2024, Brasília/DF, Brasil. 
SBC, Porto Alegre, Brasil, 145-156. DOI: https://doi.org/10.5753/wcge.2024.2966.


## About the authors

We are members of the Data Visualization and Interaction Lab (DaVInt) at PUCRS:

- Gabriel Zurawski -- Undergraduate student in Computer Science.
- Vinícius Pedroso -- Undergraduate student in Data Science and Artificial Intelligence.
- Eduarda Patricio -- Undergraduate student in Computer Science.
- Giovanna Castro -- Undergraduate student in Computer Science.
- André F. Rollwagen -- PhD student in Computer Science.
- Isabel H. Manssour -- Researcher and Professor Coordinator of DaVInt.

More information can be found at [https://www.inf.pucrs.br/davint/](https://www.inf.pucrs.br/davint/).
