ETL Pipeline SAT Automated Reporting 

1. Pipeline Strategy & Cleaning Logic
  This project focuses on a Python-driven ETL (Extract, Transform, Load) workflow designed to move beyond manual data entry. 
  My primary goal was to build a resilient system that remains stable, even if source files change locations or data quality fluctuates unexpectedly.

Dynamic Data Extraction
Instead of hardcoding a single, rigid file path, I implemented a search logic using the glob library. This is a critical feature for real-world environments where folder structures aren't always permanent.

- Self-Healing Paths: The script automatically scans system directories to locate sat-results.csv if the primary link is broken.

- Audit Trails: I utilized the logging module to keep a transparent record of exactly where the file was recovered and its initial state.

Transformation & Structural Cleanup
Raw data is rarely "database-ready." I focused on refactoring the schema to align with professional relational standards:

- Header Refactoring: I wiped out confusing or misspelled headers (like the infamous "Readng" typo) and replaced them with clean, lowercase technical names (dbn, math_avg, etc.).

- Feature Selection: I stripped away internal "noise"—such as administrative IDs and contact extensions—that only serve to clutter the final analysis.

- Value Normalization: Participation rates were converted from text strings (e.g., "85%") into standardized floats (0.85), making them compatible with mathematical operations.

Integrity & Validation
To ensure the output reached a "Gold" standard, I baked in specific business rules:

- Academic Safeguards: The SAT has strict limits (200–800). My script intercepts academic outliers—like impossible scores of 999 or -10—and neutralizes them to NaN to avoid trashing the city-wide averages.

- The DBN Constraint: I treated the dbn code as a strict Primary Key, performing a deduplication pass so that no school is counted twice in the final report.

2. SQL Integration Strategy
To prepare for the final load into a relational database (PostgreSQL), the dataset follows a specific technical architecture:

- Primary Key (PK): The dbn field is defined as the unique, immutable identifier to ensure the integrity of every school record.

- Suggested Technical Schema:

  dbn: VARCHAR(10) (PK)

  school_name: TEXT

  num_test_takers: INTEGER

  reading_avg, math_avg, writing_avg: FLOAT / INTEGER

  pct_tested: FLOAT
  
- Analytical Potential: The final artifact is optimized for JOIN operations with school demographic tables using the dbn column as the primary connector, allowing for deeper socio-economic analysis.


3. Real-World Challenges & Fixes

Challenge Detected               Solution Implemented
Inconsistent File Paths          Recursive search logic so the script "finds its own way" through the directory.
The "s" Value                    DilemmaHandled privacy-masked strings by coercing them into numeric nulls without crashing the pipeline.
Impossible Scores                Built a conditional mask to catch and nullify academic outliers (200-800 range).
Data Redundancy                  Performed deep deduplication to maintain a "Single Source of Truth."


4. Final Executive Summary (Final ETL Report)

The execution of this pipeline yielded the following verified metrics:
Status:
 Successfully integrated and validated.
 Final Dataset: 478 unique, high-quality records.
 Integrity: 100% compliance with NYC academic scoring rules and range limits.
 Output Artifact: cleaned_sat_results.csv

