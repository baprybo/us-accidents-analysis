US Traffic Accident Analysis: DOT Safety Initiative 
Project Overview
This project serves as a comprehensive data analysis for the Department of Transportation (DOT). Utilizing a dataset of over 7 million records, I applied the CRISP-DM methodology to identify spatial, temporal, and environmental factors contributing to accident severity. The ultimate goal is to provide data-driven recommendations to improve road safety and optimize emergency resource allocation.

Technical Implementation & "Big Data" Strategy
To handle a dataset of this scale (several gigabytes), I implemented advanced data engineering techniques:

AWS S3 Integration: Data was streamed directly from an S3 bucket using boto3, eliminating the need for large local file storage.

Chunked Processing: To prevent memory crashes, I processed the data in chunks of 150,000 rows. This allowed for full-scale cleaning and feature engineering (like Time_of_Day categorization) within a standard RAM environment.

Statistical Validation: I moved beyond simple charts by applying Chi-Square Tests for categorical relationships (Light vs. Severity) and ANOVA for numerical variances (Visibility vs. Severity).

Key Insights & Recommendations
The Rush Hour Surge: Analysis confirmed frequency peaks during 7-9 AM and 4-6 PM.

Recommendation: Implement dynamic emergency vehicle staging during these windows.

The Severity Paradox: While clear weather has more accidents, Nighttime accidents are statistically more severe.

Recommendation: Prioritize LED lighting upgrades and high-reflectivity markers in identified "Severity Hotspots."

Conflict Point Audit: Significant correlations were found between accident severity and Junctions/Traffic Signals.

Recommendation: Conduct engineering audits for high-risk junctions to evaluate signal timing and roundabout feasibility.

Project Structure
Project_Notebook.ipynb: The complete analysis, including S3 streaming, cleaning, and statistical testing.

requirements.txt: Necessary Python libraries (pandas, boto3, scipy, seaborn).

Interactive Tableau Dashboard: A visual exploration tool for DOT stakeholders.

 How to Run
Clone this repository.

Ensure you have AWS credentials configured for boto3.

Install dependencies: pip install -r requirements.txt.

Open the Jupyter Notebook and run all cells.
