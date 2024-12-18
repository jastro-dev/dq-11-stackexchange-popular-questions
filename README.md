# Stack Exchange Popular Data Science Questions Analysis

A data analysis project exploring popular data science questions from Stack Exchange, focusing on identifying trending topics and optimal categories for new questions.

## Project Structure

- `main_notebook.ipynb` - Primary analysis notebook containing SQL queries, data processing, and visualizations
- `data/` - Directory containing CSV data exports
  - `2024_questions.csv` - Recent questions dataset
  - `all_questions.csv` - Complete historical questions dataset
- `visualizations/` - Generated visualization outputs
  - `top_10_tags_by_use_count.png`
  - `top_10_tags_by_view_count.png`
  - `tag_cooccurrence_heatmap.png`
  - `2019_2024_monthly_number_of_deep_learning_questions.png`
  - `2019_2024_monthly_proportion_of_deep_learning_questions.png`

## Implementation Notes

The analysis combines SQL data extraction with Python-based processing and visualization using Jupyter Notebook, providing an interactive environment for data exploration and insight generation.

### Key Features

- SQL data extraction from Stack Exchange Data Explorer
- Tag analysis and cleaning
- Co-occurrence analysis
- Time series analysis
- Proportion-based trend analysis

### Implemented Analyses

1. Tag Usage Analysis
   - Most frequently used tags
   - View counts per tag
   - Tag relationship mapping

2. Deep Learning Focus
   - Identification of related tags
   - Historical trend analysis
   - Proportion analysis against total questions

3. Time Series Analysis
   - Monthly question volume tracking
   - Trend identification
   - Comparative analysis

4. Tag Relationships
   - Co-occurrence matrix
   - Heatmap visualization
   - Related tag identification

### Example Queries

```sql
SELECT Id, CreationDate, Score, ViewCount, Tags, AnswerCount, FavoriteCount
FROM Posts
WHERE PostTypeId = 1 AND CreationDate >= DATEADD(MONTH, -12, GETDATE())
ORDER BY CreationDate DESC;
```

This query demonstrates the extraction of relevant question data with proper filtering and sorting for recent timeframes.

### Development Environment

- Database: Stack Exchange Data Explorer
- Jupyter Notebook
- Python 3.12+
- Required Python packages:
  - pandas
  - matplotlib
  - seaborn
  - numpy

### Key Findings

- Deep Learning maintains consistent popularity (20-30% of questions)
- Related tags include: neural-network, pytorch, tensorflow, keras, cuda
- While absolute numbers have declined, proportional interest remains stable
- Deep Learning questions show strong engagement through views and answers