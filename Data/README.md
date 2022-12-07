# Data Files

1. NELDA.xls
    - NELDA (version 6) is a dataset of the national elections for all independent countries from 1945-2020 (Hyde & Marinov, 2012). The dataset contains 58 variables describing election events. Here NELDA serves two purposes: 1) the 58 NELDA variables are used as input features in a global model of election violence; and 2) the textual descriptions of the NELDA variables are used to filter news data relevant to risk factors of election violence.
2. DECO_v.1.0.csv
    - DECO is a georeferenced events dataset of incidents of electoral violence between 1989-2017 that resulted in at least one fatality (Fjelde & Höglund, 2022) (Figure 4). It is a derivative of the well-known and more general Uppsala Conflict Data Program Georeferenced Event Dataset (UCDP GED) (Sundberg & Melander, 2013). For the present research, DECO provides the target variable for the predictive conflict model. 
3. part_1_top_risk_factors_FINAL_BEST.csv
    - Output of Part 1. A list of the top 12 most important risk factors of historical election violence identified by the Part 1 model.
4. IDEA_ERM_Framework.xlsx
    - Outlines the IDEA Election Risk Management Framework of 26 Internal risks of election violence and 10 external risk factors.
5. nelda_look_up_plus.xlsx
    - Compared to the IDEA Election Risk Management Framework, NELDA is representative of the risks of election violence, capturing about 70% IDEA’s internal election risks and 40% of the external risk factors. This makes NELDA one of the most comprehensive resources available for the present task (Claes, 2022). This file creates this mapping between NELDA and IDEA ERM. 
6. Part_3_FINAL_BEST_performance_GridSearch.csv
    - The results of model training and search grid across 10,000+ model-parameter combinations.
7. (NOT UPLOADED HERE) Kenya News Data File
    - Code to obtain this same news data is available in Part 2 (Part 2A downloads the GDELT GKG and Part 2B scrapes the news text from the web)
    - To capture global news mentions of Kenya’s 2017 elections, a period of 15 months from August 2016 to November 2017 was defined. This is one year prior to and three months after the original August national election, which corresponds to 98 incidents of fatal election violence in the country. Scraping news mentioning Kenya in this period returned over 400,000 global news articles with an average of 200 articles per day. 
