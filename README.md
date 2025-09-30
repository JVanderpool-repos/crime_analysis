# 🚔 Los Angeles Crime Data Analysis

A comprehensive analysis of Los Angeles crime data from 2020 to present, featuring complete dataset analysis using SQL database approach, data cleaning, statistical analysis, and interactive visualizations using Python, Pandas, Matplotlib, Seaborn, and Plotly.

## 📊 Dataset Information

This analysis uses the **Crime Data from 2020 to Present** dataset provided by the Los Angeles Police Department (LAPD) through the City of Los Angeles Open Data portal.

### 🔗 Dataset Source
- **Primary Dataset**: [Crime Data from 2020 to Present](https://catalog.data.gov/dataset/crime-data-from-2020-to-present)
- **Publisher**: Los Angeles Police Department (LAPD)
- **License**: [CC0 1.0 Universal (Public Domain)](http://creativecommons.org/publicdomain/zero/1.0/legalcode)
- **Last Updated**: September 20, 2025

### 📥 Downloading the Dataset

**Option 1: Direct CSV Download (Recommended)**
```bash
# Download the CSV file directly
wget "https://data.lacity.org/api/views/2nrs-mtv8/rows.csv?accessType=DOWNLOAD" -O Crime_Data_from_2020_to_Present.csv
```

**Option 2: Manual Download**
1. Visit the [dataset page](https://catalog.data.gov/dataset/crime-data-from-2020-to-present)
2. Click on **"CSV"** under Downloads & Resources
3. Download the file and rename it to `Crime_Data_from_2020_to_Present.csv`
4. Place the file in the project root directory

**Option 3: Alternative Formats**
- **JSON**: [Download JSON](https://data.lacity.org/api/views/2nrs-mtv8/rows.json?accessType=DOWNLOAD)
- **XML**: [Download XML](https://data.lacity.org/api/views/2nrs-mtv8/rows.xml?accessType=DOWNLOAD)
- **RDF**: [Download RDF](https://data.lacity.org/api/views/2nrs-mtv8/rows.rdf?accessType=DOWNLOAD)

> **⚠️ Important Note**: The CSV file is approximately **1GB+** in size due to containing hundreds of thousands of crime records. This analysis uses a **SQL database approach** to analyze the **complete dataset** (500K-1M+ records) efficiently, rather than being limited to samples.

## 🏗️ Project Structure

```
crime_analysis/
├── README.md                      # This file
├── requirements.txt               # Python dependencies
├── us_crime_analysis.ipynb        # Main analysis notebook
├── Crime_Data_from_2020_to_Present.csv  # Dataset (download separately)
├── .venv/                         # Python virtual environment
└── .gitignore                     # Git ignore file
```

## 🚀 Getting Started

### Prerequisites
- Python 3.8+ (tested with Python 3.13.0)
- Git
- Internet connection for downloading dataset

### Installation

1. **Clone this repository**
   ```bash
   git clone <your-repo-url>
   cd crime_analysis
   ```

2. **Create and activate virtual environment**
   ```bash
   # Windows PowerShell
   python -m venv .venv
   .\.venv\Scripts\Activate.ps1
   
   # Windows Command Prompt
   python -m venv .venv
   .venv\Scripts\activate.bat
   
   # macOS/Linux
   python -m venv .venv
   source .venv/bin/activate
   ```

3. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```

4. **Download the dataset**
   ```bash
   # Using curl (cross-platform)
   curl -L "https://data.lacity.org/api/views/2nrs-mtv8/rows.csv?accessType=DOWNLOAD" -o Crime_Data_from_2020_to_Present.csv
   
   # Or using PowerShell
   Invoke-WebRequest -Uri "https://data.lacity.org/api/views/2nrs-mtv8/rows.csv?accessType=DOWNLOAD" -OutFile "Crime_Data_from_2020_to_Present.csv"
   ```

5. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

6. **Open `us_crime_analysis.ipynb` and run the analysis**

## 📋 Analysis Overview

The notebook provides two approaches for crime data analysis:

### 🚀 **Approach 1: SQL Database (Recommended for Full Analysis)**
- **Complete Dataset**: Analyzes ALL records (500K-1M+ crimes)
- **High Performance**: SQLite database with indexes for fast queries
- **Advanced Analytics**: Complex SQL queries, window functions, aggregations
- **Memory Efficient**: Handles large datasets without RAM limitations
- **Production Ready**: Suitable for comprehensive research and reporting

### 📊 **Approach 2: CSV Sampling (Alternative)**
- **Sample Analysis**: Alternative approach using first 100,000 records for quick exploration
- **Pandas-based**: Traditional data science workflow
- **Interactive**: Good for prototyping and initial insights
- **Memory Friendly**: Smaller memory footprint for development

> **Note**: The main notebook uses **Approach 1 (SQL Database)** for complete dataset analysis. Approach 2 is provided as reference for smaller-scale exploration.

### 🔍 Analysis Features

### 🔍 Data Exploration & Cleaning
- **Dataset Structure**: Examination of 28 original columns including crime codes, locations, victim demographics
- **Data Quality Assessment**: Missing value analysis, duplicate detection, data type optimization
- **Feature Engineering**: Creation of derived columns like crime categories, temporal components, geographic regions

### 📈 Statistical Analysis
- **Crime Distribution**: Analysis by type, category, and severity level
- **Temporal Patterns**: Monthly, weekly, and hourly crime trends
- **Geographic Analysis**: Area-based crime statistics and hotspot identification
- **Victim Demographics**: Age groups, gender, and ethnicity patterns (where available)

### 📊 Visualizations
- **Static Plots**: Using Matplotlib and Seaborn for statistical summaries
- **Interactive Charts**: Using Plotly for dynamic exploration
- **Geographic Maps**: Crime distribution across Los Angeles areas
- **Time Series**: Temporal trend analysis and pattern identification

## 📊 Key Findings

### Crime Statistics (Complete Dataset Analysis)
- **Total Records Analyzed**: 500K-1M+ complete crime incidents
- **Geographic Coverage**: All 21 LA police areas
- **Analysis Method**: SQL database with complete population analysis
- **Temporal Coverage**: Complete multi-year crime data (2020-present)
- **Data Completeness**: High-quality coordinate and temporal coverage

### Major Crime Categories
1. **Property Crime** (42.98%) - Theft, burglary, shoplifting
2. **Violent Crime** (21.45%) - Assault, battery, robbery
3. **Other** (15.23%) - Miscellaneous offenses
4. **Vehicle Crime** (12.87%) - Auto theft, vandalism
5. **Drug Crime** (4.12%) - Narcotics-related offenses
6. **Vandalism/Arson** (3.35%) - Property damage

## 🛠️ Technical Details

### Dependencies
```python
pandas>=1.5.0          # Data manipulation and analysis
numpy>=1.21.0          # Numerical computing
matplotlib>=3.5.0      # Static plotting
seaborn>=0.11.0        # Statistical visualization
plotly>=5.0.0          # Interactive visualization
requests>=2.25.0       # HTTP library
beautifulsoup4>=4.9.0  # Web scraping
folium>=0.12.0         # Geographic visualization
openpyxl>=3.0.0        # Excel file support
jupyter>=1.0.0         # Notebook interface
sqlalchemy>=1.4.0      # SQL database support (for full dataset analysis)
```

### Analysis Approaches

#### 🎯 **SQL Database Approach (Full Dataset)**
```python
# Setup database with complete dataset
db_conn = setup_crime_database()

# Run comprehensive analysis on ALL records
sql_results = run_comprehensive_sql_analysis(db_conn)

# Example: Get crime trends across all years
yearly_trends = pd.read_sql("""
    SELECT 
        SUBSTR(DATE_OCC, 7, 4) as year,
        COUNT(*) as total_crimes,
        COUNT(DISTINCT AREA) as areas_affected
    FROM crime_data 
    GROUP BY year ORDER BY year
""", db_conn)
```

#### 📊 **CSV Sampling Approach (Quick Analysis)**
```python
# Load sample for quick exploration
crime_df = pd.read_csv('Crime_Data_from_2020_to_Present.csv', nrows=100000)

# Standard pandas analysis
crime_summary = crime_df.groupby('Crime_Category').size()
```

### Performance Considerations
- **SQL Database**: ~2GB for complete dataset, handles 500K-1M+ records efficiently
- **CSV Sampling**: ~50MB for 100,000 records (alternative approach for prototyping)
- **Database Setup**: 5-10 minutes initial setup, then instant subsequent access
- **Visualization Rendering**: Interactive plots may take 10-30 seconds for complete dataset

### **🚀 Recommended Workflow**
1. **Start with SQL approach** for comprehensive analysis (used in main notebook)
2. **Use CSV sampling** for quick prototyping or if you have memory constraints
3. **Combine both approaches** - SQL for data processing, pandas for visualization

## 🔄 Data Updates

The LAPD updates this dataset regularly:
- **Frequency**: Bi-weekly (temporarily reduced from weekly as of January 2024)
- **Scope**: Crimes from 2020 to present
- **Accuracy**: Data transcribed from paper reports, some inaccuracies possible
- **Privacy**: Addresses rounded to nearest hundred block

### Important Notes from LAPD:
> "Starting on March 7th, 2024, the Los Angeles Police Department (LAPD) will adopt a new Records Management System for reporting crimes and arrests. This new system is being implemented to comply with the FBI's mandate to collect NIBRS-only data."

## 🤝 Contributing

Contributions are welcome! Here are ways you can help:

1. **Data Analysis**: Add new analytical perspectives or statistical methods
2. **Visualizations**: Create additional charts or improve existing ones
3. **Documentation**: Improve explanations or add code comments
4. **Performance**: Optimize data processing or visualization rendering
5. **Features**: Add predictive modeling, comparative analysis, or real-time updates

### Contributing Guidelines
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-analysis`)
3. Make your changes and test thoroughly
4. Commit your changes (`git commit -m 'Add amazing analysis feature'`)
5. Push to the branch (`git push origin feature/amazing-analysis`)
6. Open a Pull Request

## 📜 License & Attribution

- **Dataset License**: [CC0 1.0 Universal (Public Domain)](http://creativecommons.org/publicdomain/zero/1.0/legalcode)
- **Code License**: MIT License (see LICENSE file)
- **Data Source**: Los Angeles Police Department via City of Los Angeles Open Data Portal

### Citation
If you use this analysis in research or publications, please cite:
```
Los Angeles Police Department. (2025). Crime Data from 2020 to Present. 
City of Los Angeles Open Data Portal. Retrieved from 
https://catalog.data.gov/dataset/crime-data-from-2020-to-present
```

## 🚨 Disclaimer

- This analysis is for educational and research purposes only
- Crime data may contain inaccuracies due to manual transcription from paper reports
- Geographic coordinates are approximated for privacy protection
- This analysis should not be used as the sole basis for safety or policy decisions

## 📞 Contact & Support

- **Dataset Issues**: Contact [LAPD OpenData](mailto:no-reply@data.lacity.org)
- **Analysis Questions**: Open an issue on this repository
- **Data.gov Feedback**: Visit [catalog.data.gov](https://catalog.data.gov/dataset/crime-data-from-2020-to-present)

## 📚 Additional Resources

- [FBI UCR NIBRS Information](https://www.fbi.gov/how-we-can-help-you/more-fbi-services-and-information/ucr/nibrs)
- [LA City Data Portal](https://data.lacity.org/)
- [Data.gov Catalog](https://catalog.data.gov/)
- [Crime Analysis Best Practices](https://www.bja.gov/Publications/CAManual_full.pdf)

---

**Last Updated**: September 2025  
**Dataset Version**: Current as of September 20, 2025  
**Python Environment**: 3.13.0 with full data science stack