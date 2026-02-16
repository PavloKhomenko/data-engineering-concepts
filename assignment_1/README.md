# Assignment 1 - Recipe Data Analysis

## Overview
This assignment demonstrates data engineering and analysis skills using Python, DuckDB, and data visualization libraries. The analysis processes a large recipe dataset (50MB+ JSON file) to extract insights about recipe complexity, ingredient popularity, and category distributions.

## Dataset
- **Source:** `2_Recipe_json.json` (newline-delimited JSON format)
- **Size:** ~85MB
- **Structure:** Recipe data including titles, categories, ingredients, and cooking directions

## Analysis Sections

### 1. Data Loading
- Loads recipes from JSON into DuckDB in-memory database
- Validates schema and displays sample data
- Handles large JSON objects with increased size limits

### 2. Data Parsing & Transformation
- Creates normalized `recipes` table with main recipe information
- Flattens nested arrays into separate tables:
  - `recipes_ingredients` - Individual ingredients per recipe
  - `recipes_directions` - Step-by-step cooking instructions
- Implements proper relational data model with foreign key relationships

### 3. Data Quality Checks
- **Null Value Analysis:** Identifies missing data across columns
- **Duplicate Detection:** Finds duplicate recipe titles
- **Schema Validation:** Verifies ingredient/step counts match actual data

### 4. Advanced SQL Analysis (Window Functions)
Three key insights using window functions:

1. **Top Complex Recipes per Category**
   - Uses `ROW_NUMBER()` and `RANK()` to identify most complex recipes
   - Compares recipes against category averages

2. **Recipe Complexity Percentile Ranking**
   - Implements `PERCENT_RANK()` and `NTILE()` for quartile analysis
   - Classifies recipes into difficulty levels (Beginner, Intermediate, Advanced, Expert)

3. **Most Popular Ingredients by Category**
   - Uses `DENSE_RANK()` to identify top ingredients
   - Calculates usage percentages within categories

### 5. Data Visualizations
- **Bar charts:** Category distribution and recipe counts
- **Horizontal bar charts:** Average complexity by category, top ingredients
- **Box plots:** Ingredient count distribution across categories

## Key Findings
- Successfully processed and normalized large-scale recipe dataset
- Identified complexity patterns across recipe categories
- Analyzed ingredient popularity and usage trends
- Created comprehensive data quality assessment

P.S. README.md generated with AI