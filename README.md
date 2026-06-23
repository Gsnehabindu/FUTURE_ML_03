# Resume / Candidate Screening System — Future Interns ML Task 3

## Overview
This project builds an NLP-based system that scores and ranks resumes against 
a given job description, identifying skill matches and gaps to help recruiters 
shortlist candidates faster. Completed as Machine Learning Task 3 for the 
Future Interns internship program.

## Dataset
[Resume Dataset](https://www.kaggle.com/datasets/snehaanbhawal/resume-dataset) 
(Kaggle) — 2,484 real resumes across 24 job categories.

**Note on data quality:** Spot-checking samples showed that "Category" reflects 
the job role applied for, not necessarily the candidate's exact prior background 
(e.g., some candidates are career changers or entry-level applicants). A baseline 
classification test confirmed strong real signal regardless (66% accuracy vs. a 
~4% random baseline across 24 categories), validating the dataset for this task.

## What This Project Does
- Cleans and preprocesses raw resume text (lowercasing, punctuation removal, 
  stopword removal)
- Builds a reusable function that takes **any job description and category** as 
  input, then:
  - Vectorizes resumes and the job description using TF-IDF
  - Scores and ranks resumes by cosine similarity to the job description
  - Identifies specific missing skills/keywords per candidate (skill gap analysis)
- Validates the system across **three different roles** (IT, HR, Sales) to 
  confirm it generalizes — not hardcoded to one example
- Visualizes the top-ranked candidates in a bar chart

## Key Findings
- The matching system successfully ranks candidates within a role by relevance, 
  with meaningful score differentiation
- Skill gap detection surfaces concrete, actionable insights — e.g., when tested 
  against an IT Specialist role, every top-ranked candidate was missing "cloud" 
  experience specifically
- Validated across IT, HR, and Sales roles using the same underlying function, 
  confirming generalizability

## Limitations
Match scores reflect text similarity, not verified skill possession — listing a 
skill on a resume is treated the same as genuine proficiency. The missing-skills 
keyword filter is a simple heuristic and can occasionally surface generic phrasing 
alongside real skills. In production, this system should support human review, 
not replace it.

## Tech Stack
- Python, pandas
- NLTK (stopword removal)
- scikit-learn (TF-IDF, cosine similarity)
- Matplotlib (candidate ranking visualization)
- Jupyter Notebook (via VS Code)

## How to Run
1. Clone this repo
2. Create a virtual environment and install dependencies:
