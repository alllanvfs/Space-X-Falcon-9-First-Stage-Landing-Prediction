# SpaceX Falcon 9 First Stage Landing Prediction

![Falcon 9 Landing](https://i.ytimg.com/vi/D0yhZ0ZhRjo/maxresdefault.jpg)

## 📖 Project Overview

This project consists of a complete Data Science pipeline aimed at predicting whether the first stage of the SpaceX Falcon 9 rocket will land successfully. Rocket reusability is a key factor in reducing space launch costs, and predicting the probability of a successful landing based on pre-launch data is of great commercial value.

The process covers everything from data collection from multiple sources, through cleaning and exploratory analysis, to preparing a dataset to train and evaluate Machine Learning models.

---

## 📋 Table of Contents

* [Project Objectives](#-project-objectives)
* [Methodology](#-methodology)
    * [1. Data Collection](#1-data-collection)
    * [2. Data Wrangling](#2-data-wrangling)
    * [3. Exploratory Data Analysis (EDA)](#3-exploratory-data-analysis-eda)
    * [4. Predictive Analysis](#4-predictive-analysis)
* [Key Analysis Results](#-key-analysis-results)
* [🛠️ Technologies Used](#-technologies-used)

---

## 🎯 Project Objectives

The main questions this project aims to answer are:

1.  What are the key factors (launch site, orbit, payload mass, etc.) that most influence a successful landing?
2.  Which launch configurations have the highest historical success rate?
3.  Is it possible to build an accurate classification model to predict the outcome of a landing based on mission parameters?

---

## ⚙️ Methodology

The project follows a well-defined Data Science pipeline:

### 1. Data Collection

* **SpaceX REST API:** Primary data was programmatically collected from the public SpaceX API (`v4`), obtaining detailed information about launches, rockets, payloads, and launch sites.
* **Web Scraping:** To supplement and validate landing data, web scraping was performed on the Wikipedia page "List of Falcon 9 and Falcon Heavy launches" using the `BeautifulSoup` library.

### 2. Data Wrangling

* **Cleaning and Filtering:** Missing values (e.g., `PayloadMass`) were handled, and the data was filtered to focus exclusively on Falcon 9 rocket launches.
* **Feature Engineering:** The target variable `Class` was created by converting textual landing outcomes (e.g., "Success (drone ship)") into a binary format (1 for success, 0 for failure), making the problem suitable for a classification model.

### 3. Exploratory Data Analysis (EDA)

* **SQL Analysis:** SQL queries were performed to extract quick insights and answer specific business questions, such as the success rate by location or the average payload mass for NASA missions.
* **Data Visualization:** Using `Seaborn` and `Matplotlib`, charts (bar, scatter) were created to visualize the relationship between variables and the landing success rate.

### 4. Predictive Analysis

* The final dataset was prepared for Machine Learning modeling.
* Frameworks were defined to train and evaluate different classification algorithms, such as:
    * Logistic Regression
    * Support Vector Machine (SVM)
    * Decision Tree
    * K-Nearest Neighbors (KNN)
* Hyperparameter optimization using `GridSearchCV` was planned to find the best performance for each model.

---

## 📊 Key Analysis Results

The exploratory analysis revealed that the landing success rate is strongly influenced by a combination of factors, including:
* **Launch Site:** Different launch sites show distinct success rates.
* **Orbit Type:** Orbits like GTO (Geostationary Transfer Orbit) have historically presented greater difficulty for successful landings.
* **Payload Mass:** There is a visible correlation between the payload mass and the landing outcome.

---

## 🛠️ Technologies Used

* **Language:** Python
* **Analysis Libraries:** Pandas, NumPy
* **Data Collection:** Requests, BeautifulSoup
* **Database:** SQLite
* **Visualization:** Matplotlib, Seaborn, Folium
* **Machine Learning:** Scikit-learn
