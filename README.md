🍎 NYC Schools Data Analysis: Comprehensive Portfolio

📂 Detailed Structure
1. incident_analysis/
Analysis of school safety incidents across NYC public schools, focusing on trends, safety ratings, and spatial patterns.
- Key Insight: Most reports fall under "Non-criminal" incidents, suggesting safety issues are often administrative or disciplinary rather than serious crimes.
- Files: incident_analysis.ipynb, incident_analysis_clean.py, safety_insights_report.md.

2. school_directory_exploration/
Comprehensive exploration of NYC school directory data, including demographics, enrollment trends, and borough characteristics.
- Key Insight: Brooklyn holds the highest number of schools (121), while Staten Island faces the highest student density pressure per building.
- Files: school_exploration.ipynb, demographic_analysis.py, visuals/.

3. database_queries/
SQL-based analysis focusing on academic performance correlations and demographic patterns using Python for complex queries.
- Key Insight: Manhattan stands out for inclusive education, with resource hubs like East Side Community School serving up to 28.8% Special Education (SPED) students.
- Files: database_queries.ipynb, insightful_queries.sql, query_analysis.md.

4. database_population/
An automated ETL pipeline for cleaning and loading SAT results data into a relational PostgreSQL database.
- Key Insight: Implemented "self-healing" path logic using the glob library to ensure pipeline stability if file locations change.
- Files: clean_sat_data.py, cleaned_sat_results.csv, sat_schema.sql.

📊 Key Findings & Strategic Observations
School Safety & Geography: 
- Brooklyn and the Bronx together account for over 58% of all recorded incidents. While Brooklyn has the most incidents, 
  the Bronx has the highest incident rate per school at 31% when normalized.
- Infrastructure Pressure: Staten Island operates at the highest density with an average of 1,847 students per school, 
  compared to only 490 students per school in the Bronx.
- Access Equity: 
  Brooklyn offers robust access, with 100% of its 121 high schools providing entry points for the 9th grade.
- Data Integrity: 
  The ETL pipeline successfully validated 478 unique records, correcting typos like "Readng" and neutralizing academic outliers 
  (scores outside the 200-800 range) to ensure high-quality reporting.

🛠️ Technical Stack
- Data Processing: Python 3.8+ (Pandas, NumPy), Jupyter Notebooks, SQLAlchemy.
- Database Management: PostgreSQL, focusing on relational standards and DBN code as a strict Primary Key.
- Visualization: Matplotlib, Seaborn for statistical plotting.
- Automation: glob library for dynamic file extraction and logging for transparent audit trails.

📈 Strategic Recommendations
1. Targeted Expansion: Prioritize infrastructure investment in Staten Island and Queens to alleviate extreme student density per building.

2. Density-Based Budgeting: Shift resource allocation from a "per-school" model to a "density-adjusted" model to support boroughs with higher student loads.
