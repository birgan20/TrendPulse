# TrendPulse – Part 3: Visualization and Exploratory Data Analysis

## 1. Project Overview

Part 3 of TrendPulse focuses on visualizing YouTube trending video data and performing Exploratory Data Analysis (EDA).

The objective is to understand video popularity, audience engagement, category performance, country differences, trending duration, and content performance patterns.

## 2. Dataset Used

The following country datasets were used:

- USvideos.csv – USA
- GBvideos.csv – Great Britain
- INvideos.csv – India
- FRvideos.csv – France
- categories.csv – Category lookup data

The four country datasets were combined into one Pandas DataFrame. A country column was added to identify the origin of each record.

**Total records after cleaning:** [Enter actual row count]

**Number of countries:** 4

## 3. Data Preparation and Cleaning

The following preparation steps were performed:

1. Loaded country CSV files using Pandas.
2. Combined the country datasets using `pd.concat()`.
3. Added a country column to each dataset.
4. Converted views, likes, dislikes, and comment_count into numeric data types.
5. Converted trending_date and publish_time into datetime formats.
6. Checked missing values and duplicate records.
7. Removed duplicate records based on video_id, trending_date, and country.
8. Removed records without essential analysis values.
9. Merged the categories lookup table to obtain category names.

Missing numeric values were not automatically replaced with zero because missing values and genuine zero values have different meanings.

## 4. Matplotlib Visualizations

Five Matplotlib charts were created.

### Chart 1: Top 10 Categories by Average Views

**Purpose:** Compare the average views received by different video categories.

**Interpretation:** The category with the highest average views was [Enter category]. This indicates that [Enter your observation].

### Chart 2: Distribution of YouTube Video Views

**Purpose:** Understand the distribution of video views using a histogram and logarithmic scale.

**Interpretation:** The distribution was [Enter your observation, such as right-skewed]. This indicates that [Explain your finding].

### Chart 3: Relationship Between Views and Likes

**Purpose:** Examine the relationship between video views and likes using a scatter plot.

**Interpretation:** The relationship between views and likes appeared [positive/negative/weak]. This suggests that [Enter your observation].

### Chart 4: Daily YouTube Trending Records

**Purpose:** Identify changes in the number of trending records over time.

**Interpretation:** The number of trending records [increased/decreased/fluctuated] during [Enter the period]. This indicates that [Enter your observation].

### Chart 5: Distribution of Views by Category

**Purpose:** Compare the median, spread, and outliers in video views across categories using a box plot.

**Interpretation:** The category with the highest median views was [Enter category]. The chart also showed [Enter your observation about spread or outliers].

## 5. Plotly Interactive Visualizations

Two interactive charts were created using Plotly.

### Chart 6: Interactive Views vs Likes by Category

This scatter plot displays views and likes, with video categories represented using different colours.

Users can hover over individual points to view video titles and countries.

**Observation:** [Enter your finding.]

### Chart 7: Average Views by Category Across Countries

This grouped bar chart compares average views across countries and video categories.

**Observation:** [Enter your finding about country differences.]

## 6. Statistical Analysis

Mean, median, and mode were calculated for views and likes.

| Metric | Mean | Median | Mode |
|---|---|---|---|
| Views | [Value] | [Value] | [Value] |
| Likes | [Value] | [Value] | [Value] |

**Skewness interpretation:**

[Explain whether views and likes are right-skewed, left-skewed, or approximately symmetric based on the results.]

## 7. Outlier Detection Using IQR

The Interquartile Range method was used to identify outliers in views and likes.

Formula:

- IQR = Q3 − Q1
- Lower limit = Q1 − 1.5 × IQR
- Upper limit = Q3 + 1.5 × IQR

| Column | Number of Outliers |
|---|---:|
| Views | [Value] |
| Likes | [Value] |

**Decision:** Valid high-view videos were retained because they may represent genuine viral content. Only records confirmed to be incorrect should be removed.

## 8. Correlation Analysis

A correlation matrix and heatmap were created using:

- Views
- Likes
- Dislikes
- Comment count
- Days to trend

**Two strongest correlations:**

1. [Variable 1] and [Variable 2]: [Correlation value and interpretation].
2. [Variable 3] and [Variable 4]: [Correlation value and interpretation].

Correlation identifies relationships between variables but does not prove causation.

## 9. Video Performance Funnel

Four stages were used to evaluate video performance:

1. All unique videos that appeared in trending records.
2. Videos with peak views above the median.
3. Videos with peak views above the 90th percentile.
4. Videos above the 90th percentile with at least 1,000 comments.

| Funnel Stage | Video Count |
|---|---:|
| All trending videos | [Value] |
| Above median peak views | [Value] |
| Above 90th percentile | [Value] |
| Above 90th percentile + 1,000 comments | [Value] |

**Interpretation:** The largest drop-off occurred between [Stage] and [Stage]. This indicates that [Explain your observation].

## 10. Trending Retention Analysis

Retention was measured by treating the first observed trending appearance as Day 1.

| Observed Trending Day | Retention Percentage |
|---|---:|
| Day 2 | [Value]% |
| Day 3 | [Value]% |
| Day 5 | [Value]% |
| Day 7 | [Value]% |

**Interpretation:** By observed Day 7, [Value]% of video-country records remained in the trending dataset. The comparison between [Category 1] and [Category 2] showed that [Enter finding].

Note: Observed trending days represent successive recorded appearances, not necessarily consecutive calendar days.

## 11. Cohort Analysis

Videos were grouped according to their first trending month.

Average peak views were calculated for each monthly cohort.

**Finding:** The cohort with the highest average peak views was [Enter month]. It contained [Enter number] videos.

Cohort sizes were considered when interpreting the results because small groups may produce less reliable averages.

## 12. Content Strategy Briefing

[Write your final 5–8 sentence business briefing using evidence from the charts, funnel, retention, and country comparisons.]

The briefing should discuss:

- Best-performing categories.
- Distribution of views.
- Relationship between views and engagement.
- Funnel conversion and largest drop-off.
- Trending retention.
- Differences across countries.
- Recommended content strategy.
- Limitations of the analysis.

## 13. Limitations

1. The analysis uses historical trending video records, not all YouTube videos.
2. High views do not necessarily indicate positive audience response.
3. Repeated daily trending records can cause the same video to appear multiple times in record-level charts.
4. Correlation does not prove causation.
5. Observed trending-day retention may differ from actual consecutive calendar-day retention.
6. The findings do not guarantee future video performance.

## 14. How to Run the Project

1. Open Google Colab.
2. Upload `TrendPulse_Part3.ipynb`.
3. Upload the four country CSV files and categories.csv into the `data` folder.
4. Install the required libraries.
5. Run the notebook from top to bottom.
6. Review the charts, statistical results, funnel, retention, and cohort analysis.

## 15. Requirements

- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly

Run the following command to install the dependencies:

`pip install -r requirements.txt`