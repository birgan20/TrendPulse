# TrendPulse – Part 1: Python Foundations

## 1. Project Overview

TrendPulse is a data analysis project that explores trending YouTube videos across different countries using Python.

The main objective of Part 1 is to understand the dataset, perform basic data cleaning, work with Python data structures, and classify videos based on their views and engagement levels.

## 2. Countries Selected

For this project, I selected YouTube trending video datasets from three countries:

- **USA:** USvideos.csv
- **United Kingdom:** GBvideos.csv
- **India:** INvideos.csv

I also used `categories.csv` to understand the video category information.

These datasets help compare trending videos and audience engagement across different countries.

## 3. Loading the Data

I used the Pandas library to load the CSV files.

```python
import pandas as pd

us_data = pd.read_csv("data/USvideos.csv")
gb_data = pd.read_csv("data/GBvideos.csv")
in_data = pd.read_csv("data/INvideos.csv")
categories = pd.read_csv("data/categories.csv")
```

I converted the DataFrames into lists of dictionaries using:

```python
us_records = us_data.to_dict("records")
gb_records = gb_data.to_dict("records")
in_records = in_data.to_dict("records")
```

I combined the records from all three countries into a single list for analysis.

## 4. Data Cleaning

The following data cleaning steps were performed:

- Checked the dataset for missing values.
- Converted numerical columns such as `views`, `likes`, `dislikes`, and `comment_count` into integer values.
- Replaced invalid numerical values with 0 when conversion failed.
- Checked and handled records with zero likes and dislikes.
- Identified videos where ratings were disabled.
- Prepared the cleaned records for further analysis.

## 5. Python Data Structures Used

I used four important Python data structures in this project.

### Lists
Used to store all video records and combine records from different countries.

### Tuples
Used to store fixed video field names or groups of related values that should not be modified.

### Sets
Used to identify unique video IDs, avoid duplicate identifiers, and find common IDs across datasets.

### Dictionaries
Used to store video information as key-value pairs and maintain category, channel, and country counts.

These data structures helped organize and process the data efficiently.

## 6. Video Classification Thresholds

I classified videos based on their view counts and like ratios.

Like Ratio = Likes / (Likes + Dislikes)

The following thresholds were selected:

| Classification | Conditions |
|---|---|
| Viral Hit | Views >= 1,000,000 and Like Ratio >= 0.90 |
| Steady Performer | Views >= 100,000 and Like Ratio >= 0.75 |
| Divisive | Like Ratio < 0.50 |
| Low Engagement | Does not meet the above conditions |
| Unrated | Ratings disabled or Likes + Dislikes = 0 |

These thresholds help identify highly popular videos, consistently performing videos, and videos receiving mixed audience reactions.

## 7. How to Run the Notebook

1. Open Google Colab: https://colab.research.google.com/
2. Open the `TrendPulse.ipynb` notebook.
3. Upload the project data files or make sure they are available in the expected Google Drive folder.
4. Install the required libraries if they are not already available.
5. Run the notebook cells sequentially from top to bottom.
6. Review the outputs and video classification results.

Required libraries:

- Pandas
- NumPy
- Matplotlib
- Seaborn

## 8. Conclusion

In Part 1 of TrendPulse, I learned how to load and clean real-world YouTube datasets, use Python lists, tuples, sets, and dictionaries, and apply classification rules using conditional statements.

This part provides the foundation for further data analysis and visualization in the upcoming project sections.