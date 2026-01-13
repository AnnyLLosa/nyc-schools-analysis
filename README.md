🍎 NYC Schools Data Analysis: Strategic Portfolio



📝 Project Overview
This project presents an in-depth, multidimensional analysis of the New York City public school system. Through a five-stage workflow, I transformed raw datasets into a structured information ecosystem using Python-driven ETL pipelines, Statistical Analysis, and SQL Querying. The goal was to uncover critical insights into school safety, infrastructure density, and academic equity to support data-driven strategic recommendations.



📂 Detailed Structure by Focus Area

🛠️ School Safety Analysis (Git & GitHub Fundamentals)
Analyzed safety trends across 1,891 unique schools using a dataset of 6,312 records and over 28,000 recorded incidents.


Key Insight: Most reports fall under "Non-criminal" incidents, suggesting many safety issues are administrative or disciplinary rather than serious crimes.


Geographic Trends: Brooklyn and the Bronx together account for over 58% of all incidents.


The Bronx Context: While Brooklyn has the highest raw total, the Bronx has the highest incident rate per school at 31% when normalized.


Files: incident_analysis.ipynb, incident_analysis_clean.py, safety_insights_report.md.



🐍 School Directory Exploration (Python Basics)
Explored demographics and enrollment trends, highlighting the stark contrast in school density across boroughs.


Infrastructure Pressure: Staten Island faces the highest student density with an average of 1,847 students per school, while the Bronx has the lowest average at 490 students.


Academic Access: Brooklyn holds the highest number of schools (121), and 100% of these schools provide critical access to 9th grade.


Files: school_exploration.ipynb, demographic_analysis.py, and demographic maps.




🐘 Database Queries (PostgreSQL Practice)
Utilized SQL logic via Python to identify specialized resource hubs and bilingual program needs.


Manhattan Snapshot: Verified records via INNER JOIN show a 7.57% average for English Language Learners (ELL) in Manhattan.


Inclusive Leadership: Manhattan shows strong leadership in inclusive education, with schools like East Side Community School serving Special Education (SPED) populations of up to 28.8%.


Files: database_queries.ipynb, insightful_queries.sql, query_analysis.md.



⚙️ ETL & Integration
Developed a resilient ETL pipeline to clean and load SAT results into a relational database.


Resilient Strategy: Implemented "Self-Healing Paths" using the glob library to automatically locate datasets even if primary folder structures change.


Data Integrity: Successfully corrected misspelled headers (e.g., "Readng") and neutralized academic outliers outside the valid 200–800 SAT range.


Files: clean_sat_data.py, cleaned_sat_results.csv (containing 478 unique records), and sat_schema.sql.



🚀 Project Wrapping & Publishing
Finalized the repository structure to reflect professional functionality, ensuring the DBN code serves as a strict Primary Key for relational integrity.


Files: requirements.txt (including pandas, matplotlib, seaborn, sqlalchemy, and ipykernel), root README.md, and project assets/.



📈 Strategic Recommendations

1. Targeted Expansion: Prioritize infrastructure investment in Staten Island and Queens, as they handle significantly more students per building than other boroughs.


2. Density-Based Budgeting: Shift resource allocation to "density-adjusted" funding for boroughs like Staten Island where student loads are nearly triple those of the Bronx.
