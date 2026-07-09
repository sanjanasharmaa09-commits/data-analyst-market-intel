Data Analyst Job Market Intelligence Dashboard

An end-to-end data analytics project that scrapes live Data Analyst job postings from Naukri.com, cleans and analyzes the data, and visualizes hiring trends, in-demand skills, and salary patterns through an interactive Power BI dashboard.


Problem Statement

Most data analyst portfolio projects rely on static, pre-cleaned datasets from Kaggle — the same Netflix, HR Attrition, or Superstore datasets appear on countless resumes. This project takes a different approach: instead of analyzing historical data, it captures a live snapshot of the current job market to answer a practical question — what skills are companies actually hiring for right now, and how do those skills correlate with salary and location?

The goal was to build something that not only demonstrates technical skill, but also generates insights that could genuinely guide a job search — including my own.


Tech Stack

CategoryTools UsedWeb ScrapingPython, Selenium, BeautifulSoupData Cleaning & AnalysisPandas, PythonVisualizationPower BI, DAXVersion ControlGit, GitHub


Methodology


Data Collection — Scraped 299+ live Data Analyst job postings from Naukri.com using Selenium (chosen over simple HTTP requests because the site renders listings dynamically via JavaScript).
Data Cleaning — Removed duplicates, parsed experience ranges and salary bands into numeric fields, standardized location names, and filtered raw scraped skill tags against a curated technical skill whitelist to remove noise.
Analysis — Identified the most in-demand skills, skill co-occurrence patterns (which skills appear together), salary correlation by skill, and geographic hiring concentration.
Visualization — Built a single-page interactive Power BI dashboard combining KPI cards, a treemap, a skill-salary bar chart, a geographic map, and a skill-pairing table, with slicers for experience level and company tier.



Key Insights


Data Analysis, Python, SQL, and Power BI emerged as the most consistently requested skills across postings.
Skills like SQL and Power BI, and Python and SQL, frequently appear together in the same job posting — suggesting employers value combined toolsets over single-skill expertise.
Certain skills (e.g., cloud/statistics-related skills) correlated with noticeably higher average salary bands compared to baseline analyst postings.
Hiring activity is concentrated in a handful of metro cities, with Bengaluru and Hyderabad among the top locations.


(Exact percentages and figures are available in the dashboard.)


Challenges Faced


JavaScript-rendered content: Initial scraping attempts using requests + BeautifulSoup returned empty results because Naukri.com loads job listings dynamically. Switched to Selenium to render the full page before extraction.
Broken pagination: Direct URL manipulation for page numbers (-2, -3, etc.) silently reloaded page 1 instead of advancing, resulting in duplicate data. Fixed by programmatically clicking the "Next" button instead, using a JavaScript-executed click to bypass an intercepting overlay element.
Noisy skill tags: Naukri's auto-generated skill tags included generic, non-technical phrases (e.g., "workflow," "Vendor") alongside genuine skills. Solved by filtering extracted tags against a manually curated whitelist of valid technical skills.
Missing fields identified mid-analysis: Company name, rating, salary, and posting date were not part of the initial scrape. Rather than treating this as a full restart, the scraper was extended once, incorporating all missing fields in a single additional run.



Dashboard Preview

(Insert dashboard screenshot here)

The dashboard includes:


KPI cards (Total Jobs, Unique Companies, Unique Locations, Average Salary)
Treemap of top in-demand skills
Bar chart: skills associated with the highest average salary
Table of most common skill combinations
Geographic map of job concentration by city
Donut chart of experience-level distribution
Interactive slicers for experience level and company tier (MNC vs. Other)



Personal Upskilling Note

This analysis surfaced skill gaps in my own toolkit that I addressed directly — closing the loop between market research and personal preparation, rather than treating the project as a purely academic exercise.


Future Scope


Extend the analysis to include internship listings for a job-vs-internship skill comparison.
Add sentiment/tone analysis on job descriptions.
Automate the scraper to run on a schedule and track how skill demand shifts over time.



Author

Sanjana Sharma
Final Year BCA (AI & Data Science), Graphic Era Hill University
GitHub: sanjanasharmaa09
