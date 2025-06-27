# 🚨 Crime Data Analysis with Apache Spark

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Apache Spark](https://img.shields.io/badge/Apache%20Spark-3.2.0-orange.svg)](https://spark.apache.org/)
[![Kaggle](https://img.shields.io/badge/Kaggle-Notebook-red.svg)](https://www.kaggle.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📋 Table of Contents

- [📊 Project Overview](#-project-overview)
- [🎯 Key Objectives](#-key-objectives)
- [🛠️ Technology Stack](#️-technology-stack)
- [📈 Dataset Information](#-dataset-information)
- [🔍 Analysis Implemented](#-analysis-implemented)
  - [Total Crimes by County](#total-crimes-by-county)
  - [Monthly Crime Trends](#monthly-crime-trends)
  - [Crime Type Analysis](#crime-type-analysis)
- [🎨 Visualizations Created](#-visualizations-created)
- [🚀 Technical Implementation](#-technical-implementation)
- [🛠️ Setup and Installation](#️-setup-and-installation)
- [👨‍💻 Author](#-author)
- [📄 License](#-license)
- [📞 Contact](#-contact)

---

## 📊 Project Overview

This project demonstrates data analysis capabilities using **Apache Spark** to process and analyze crime data from three UK counties: **Kent**, **Leicestershire**, and **Derbyshire**. The analysis covers the entire year of 2022, providing insights into crime patterns and trends across these regions.

### 🎯 Key Objectives
- **Big Data Processing**: Handle crime datasets using Apache Spark
- **Data Preprocessing**: Clean, transform, and standardize crime data
- **Statistical Analysis**: Perform descriptive analytics on crime patterns
- **Data Visualization**: Create charts and graphs for data insights

## 🛠️ Technology Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| **Apache Spark** | 3.2.0 | Distributed computing and data processing |
| **PySpark** | 3.2.0 | Python API for Apache Spark |
| **Python** | 3.8+ | Primary programming language |
| **Pandas** | Latest | Data manipulation and analysis |
| **Matplotlib** | Latest | Data visualization |
| **Kaggle Notebooks** | Latest | Cloud-based development environment |

## 📈 Dataset Information

- **Source**: UK Police Data Portal
- **Time Period**: January 2022 - December 2022
- **Geographic Coverage**: 3 UK Counties (Kent, Leicestershire, Derbyshire)
- **Data Format**: CSV files (36 files - 12 months × 3 counties)
- **Platform**: Kaggle Datasets

## 🔍 Analysis Implemented

### Total Crimes by County
- Calculated the total number of crimes for each county using Spark SQL.

### Monthly Crime Trends
- Computed monthly crime counts for each county.
- Identified peak and lowest crime months for each county.

### Crime Type Analysis
- Ranked crime types by frequency for each county.
- Identified most and least common crime types per county.

## 🎨 Visualizations Created
- **Line Chart**: Monthly crime trends across all three counties.
- **Bar Chart**: Crime type comparisons between counties.
- **Pie Charts**: Crime type distribution for each county.

## 🚀 Technical Implementation
- Data loading and preprocessing with PySpark.
- DataFrame operations: renaming, filtering, grouping.
- Spark SQL for analytical queries.
- Conversion to Pandas for visualization.
- Visualizations with matplotlib.

## 🛠️ Setup and Installation

### On Kaggle
1. Open the notebook in Kaggle.
2. Ensure the crime dataset is attached.
3. Run all cells sequentially.

### Local (Optional)
1. Clone the repository.
2. Install dependencies: `pip install pyspark==3.2.0 pandas matplotlib`
3. Download the dataset from Kaggle and update the file path in the notebook.
4. Run the notebook with Jupyter or your preferred environment.

## 👨‍💻 Author

**Divyansh Singh**
- **Course**: CTEC3702 - Big Data Analytics
- **Skills**: Apache Spark, Python, Data Analysis, SQL, Cloud Computing

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

- **Email**: divyanshsingh1800@gmail.com
- **LinkedIn**: https://www.linkedin.com/in/divyanshsingh28/
- **GitHub**: https://github.com/Divyansnh

---

<div align="center">

**⭐ Star this repository if you found it helpful!**

*Built with ❤️ using Apache Spark and Python on Kaggle*

</div> 
