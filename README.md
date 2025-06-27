# 🚨 Crime Data Analysis with Apache Spark

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Apache Spark](https://img.shields.io/badge/Apache%20Spark-3.2.0-orange.svg)](https://spark.apache.org/)
[![Kaggle](https://img.shields.io/badge/Kaggle-Notebook-red.svg)](https://www.kaggle.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

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

### Data Source
- **Source**: UK Police Data Portal
- **Time Period**: January 2022 - December 2022
- **Geographic Coverage**: 3 UK Counties (Kent, Leicestershire, Derbyshire)
- **Data Format**: CSV files (36 files - 12 months × 3 counties)
- **Platform**: Kaggle Datasets

### Data Schema
| Column | Description | Data Type |
|--------|-------------|-----------|
| `Crime_ID` | Unique identifier for each crime | String |
| `Month` | Month and year of crime | String |
| `Reported_By` | Police force that reported the crime | String |
| `Falls_Within` | Police force area | String |
| `Longitude` | Geographic longitude | Double |
| `Latitude` | Geographic latitude | Double |
| `Location` | Street location description | String |
| `LSOA_Code` | Lower Layer Super Output Area code | String |
| `LSOA_Name` | Lower Layer Super Output Area name | String |
| `Crime_Type` | Category of crime committed | String |
| `Last_Outcome_Category` | Outcome of the investigation | String |
| `Context` | Additional context information | String |

## 🔍 Analysis Implemented

### 📊 Crime Statistics by County
| County | Total Crimes | Percentage |
|--------|-------------|------------|
| **Kent** | 200,945 | 47.0% |
| **Leicestershire** | 115,179 | 27.0% |
| **Derbyshire** | 110,805 | 26.0% |

### 📅 Monthly Crime Trends Analysis
**Kent County:**
- **Peak Month**: August 2022 (18,365 crimes)
- **Lowest Month**: December 2022 (14,976 crimes)

**Leicestershire County:**
- **Peak Month**: August 2022 (10,373 crimes)
- **Lowest Month**: February 2022 (8,482 crimes)

**Derbyshire County:**
- **Peak Month**: May 2022 (10,140 crimes)
- **Lowest Month**: December 2022 (8,008 crimes)

### 🚨 Crime Type Analysis by County

**Kent County - Most Common Crimes:**
1. **Violence and Sexual Offences** - 83,341 incidents
2. **Anti-social Behaviour** - 27,904 incidents
3. **Criminal Damage and Arson** - 19,936 incidents

**Leicestershire County - Most Common Crimes:**
1. **Violence and Sexual Offences** - 44,019 incidents
2. **Public Order** - 13,766 incidents
3. **Criminal Damage and Arson** - 10,963 incidents

**Derbyshire County - Most Common Crimes:**
1. **Violence and Sexual Offences** - 41,878 incidents
2. **Anti-social Behaviour** - 23,038 incidents
3. **Public Order** - 10,198 incidents

## 🎨 Visualizations Created

### 📈 Charts Implemented
- **Line Charts**: Monthly crime trends across all three counties
- **Bar Charts**: Crime type comparisons between counties
- **Pie Charts**: Crime distribution breakdown for each county

### 📊 Key Insights Visualized
1. **Monthly Trends**: Seasonal patterns in crime rates across counties
2. **County Comparisons**: Relative crime levels and types
3. **Crime Type Distribution**: Detailed breakdown of different crime categories per county

## 🚀 Technical Implementation

### Data Processing Pipeline
```python
# 1. Data Loading from Kaggle Dataset
df = spark.read.csv("/kaggle/input/crime-dataset/*.csv", 
                    header=True, inferSchema=True)

# 2. Data Preprocessing - Column Renaming
df = df.toDF("Crime_ID", "Month", "Reported_By", "Falls_Within", 
             "Longitude", "Latitude", "Location", "LSOA_Code", 
             "LSOA_Name", "Crime_Type", "Last_Outcome_Category", "Context")

# 3. County Standardization
df = df.withColumn("County", 
    when(col("Reported_By") == "Kent Police", "Kent")
    .when(col("Reported_By") == "Leicestershire Police", "Leicestershire")
    .when(col("Reported_By") == "Derbyshire Constabulary", "Derbyshire")
    .otherwise(None))

# 4. SQL Analysis
df.createOrReplaceTempView("CrimeDatabase")
results = spark.sql("""
    SELECT County, COUNT(*) AS total_crimes
    FROM CrimeDatabase
    GROUP BY County
""")
```

### Key Spark Operations Used
- **DataFrame Operations**: Column renaming, filtering, grouping
- **Spark SQL**: Complex analytical queries for crime statistics
- **Conditional Logic**: County mapping using when/otherwise
- **Data Aggregation**: Count operations and grouping by multiple dimensions

## 📋 Project Structure

```
CTEC3702-Crime-Data-Spark-Analysis/
├── problem-specification-part-a.ipynb  # Main analysis notebook (Kaggle)
└── README.md                           # Project documentation
```

## 🎯 Key Achievements

### ✅ Technical Skills Demonstrated
- **Big Data Processing**: Successfully processed crime datasets using Apache Spark
- **Data Engineering**: Implemented data preprocessing and transformation pipelines
- **SQL Proficiency**: Complex analytical queries using Spark SQL
- **Data Visualization**: Created comprehensive visualizations using matplotlib
- **Statistical Analysis**: Descriptive analytics and trend analysis
- **Cloud Computing**: Utilized Kaggle's cloud infrastructure for big data processing

### 📊 Analysis Delivered
- **Pattern Recognition**: Identified seasonal crime patterns across counties
- **Comparative Analysis**: Detailed comparison of crime types and frequencies
- **Data Insights**: Clear understanding of crime distribution and trends
- **Visual Reporting**: Professional charts and graphs for data presentation

## 🛠️ Setup and Installation

### Prerequisites
- Kaggle account
- Access to the crime dataset on Kaggle
- Basic knowledge of Python and Apache Spark

### Running the Analysis on Kaggle
1. **Access the Notebook**: Open the notebook on Kaggle
2. **Dataset Access**: Ensure the crime dataset is attached to your notebook
3. **Environment**: Kaggle provides pre-configured environment with Python, Spark, and required libraries
4. **Execution**: Run all cells sequentially to perform the analysis

### Local Setup (Optional)
If you want to run this locally:
```bash
# 1. Clone the repository
git clone https://github.com/yourusername/CTEC3702-Crime-Data-Spark-Analysis.git
cd CTEC3702-Crime-Data-Spark-Analysis

# 2. Install dependencies
pip install pyspark==3.2.0 pandas matplotlib jupyter

# 3. Download the dataset from Kaggle
# 4. Update the file path in the notebook
# 5. Launch Jupyter Notebook
jupyter notebook
```

## 📊 Sample Results

### Crime Distribution by County
```
+--------------+------------+
|        County|total_crimes|
+--------------+------------+
|          Kent|      200945|
|Leicestershire|      115179|
|    Derbyshire|      110805|
+--------------+------------+
```

### Monthly Crime Trends (Kent)
```
+-------+---------------------+
|  Month|Crimes_per_Month_Kent|
+-------+---------------------+
|2022-08|                18365|  ← Peak
|2022-12|                14976|  ← Lowest
+-------+---------------------+
```

## 🔮 Future Enhancements

### Potential Improvements
- **Machine Learning**: Predictive modeling for crime forecasting
- **Real-time Processing**: Stream processing for live crime data
- **Advanced Visualization**: Interactive dashboards using Plotly/Dash
- **Geospatial Analysis**: Advanced mapping with Folium/GeoPandas
- **Performance Optimization**: Spark tuning and optimization

### Additional Analysis Opportunities
- **Temporal Analysis**: Day-of-week and time-of-day patterns
- **Correlation Analysis**: Weather, events, and crime relationships
- **Predictive Analytics**: Crime forecasting models
- **Resource Optimization**: Police resource allocation recommendations

## 👨‍💻 Author

**Divyansh Singh**
- **Course**: CTEC3702 - Big Data Analytics
- **Skills**: Apache Spark, Python, Data Analysis, SQL, Cloud Computing

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Contact

- **Email**: divyanshsingh1800@gmail.com
- **LinkedIn**: https://www.linkedin.com/in/divyanshsingh28/
- **GitHub**: https://github.com/Divyansnh

---

<div align="center">

**⭐ Star this repository if you found it helpful!**

*Built using Apache Spark and Python on Kaggle*

</div> 
