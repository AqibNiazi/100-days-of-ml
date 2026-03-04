# Lecture 34 – Handling Date & Time Variables in Machine Learning

(Practical Implementation using Pandas & NumPy)

## Why Date & Time Features Are Important?

Date and time variables contain hidden patterns like:

- Seasonality
- Trends
- Day-of-week effects
- Monthly patterns
- Time gaps between events

Raw date values are not useful directly for machine learning models.
We must extract meaningful features.

## Common Date & Time Problems

- Stored as string (`object` type)
- Multiple formats
- Time zone issues
- Missing values
- Need feature extraction

## Step 1: Convert to Datetime Format (Pandas)

Convert string to datetime:

```python
import pandas as pd

df['date'] = pd.to_datetime(df['date'])
```

If format is specific:

```python
df['date'] = pd.to_datetime(df['date'], format='%Y-%m-%d')
```

## Extracting Features from Datetime

Assume:

```python
df['date'] = pd.to_datetime(df['date'])
```

### Basic Date Features

```python
df['year'] = df['date'].dt.year
df['month'] = df['date'].dt.month
df['day'] = df['date'].dt.day
df['day_of_week'] = df['date'].dt.dayofweek
df['week_of_year'] = df['date'].dt.isocalendar().week
df['quarter'] = df['date'].dt.quarter
```

### Time Features

If datetime contains time:

```python
df['hour'] = df['date'].dt.hour
df['minute'] = df['date'].dt.minute
df['second'] = df['date'].dt.second
```

## Extracting Weekend Information

```python
df['is_weekend'] = df['date'].dt.dayofweek >= 5
```

## Handling Time Differences (Very Important Feature)

Calculate age of account:

```python
df['days_passed'] = (pd.Timestamp.today() - df['date']).dt.days
```

Difference between two columns:

```python
df['difference'] = (df['date2'] - df['date1']).dt.days
```

## Extracting Month Start / End

```python
df['is_month_start'] = df['date'].dt.is_month_start
df['is_month_end'] = df['date'].dt.is_month_end
```

## Handling Cyclical Features (Important Concept)

Months and hours are cyclical:

- December → January
- 23:00 → 00:00

If we encode month directly:

December = 12
January = 1

The model thinks they are far apart, which is incorrect.

### Solution: Use Sine & Cosine Transformation (NumPy)

Example for Month:

```python
import numpy as np

df['month_sin'] = np.sin(2 * np.pi * df['month'] / 12)
df['month_cos'] = np.cos(2 * np.pi * df['month'] / 12)
```

Example for Hour:

```python
df['hour_sin'] = np.sin(2 * np.pi * df['hour'] / 24)
df['hour_cos'] = np.cos(2 * np.pi * df['hour'] / 24)
```

This preserves cyclical relationships.

## Handling Missing Date Values

Options:

- Drop rows
- Fill with median date
- Fill with specific date
- Create missing indicator column

Example:

```python
df['date'].fillna(df['date'].median(), inplace=True)
```

## Sorting and Indexing by Date

For time series:

```python
df = df.sort_values('date')
df.set_index('date', inplace=True)
```

## Feature Engineering Strategy for Dates

Whenever you see a date column:

Step 1: Convert to datetime
Step 2: Extract useful components
Step 3: Create difference features
Step 4: Handle cyclical variables properly
Step 5: Drop original column (if needed)

## Complete Practical Example

Original column:

```python
df['purchase_date']
```

Feature Engineering:

```python
df['year'] = df['purchase_date'].dt.year
df['month'] = df['purchase_date'].dt.month
df['day_of_week'] = df['purchase_date'].dt.dayofweek
df['is_weekend'] = df['day_of_week'] >= 5
df['days_since_purchase'] = (pd.Timestamp.today() - df['purchase_date']).dt.days
```

Optional cyclical encoding:

```python
df['month_sin'] = np.sin(2 * np.pi * df['month'] / 12)
df['month_cos'] = np.cos(2 * np.pi * df['month'] / 12)
```

## Key Takeaways

- Never use raw date directly
- Always convert to datetime
- Extract meaningful components
- Time differences are powerful features
- Use sine/cosine for cyclical variables
- Drop original date if not required

## Summary

Handling date and time variables is mostly practical feature engineering.
The power comes from extracting:

- Year
- Month
- Day
- Weekday
- Time components
- Time differences
- Cyclical encodings

Proper date feature engineering significantly improves model performance in:

- Time-series problems
- Sales forecasting
- Customer churn prediction
- Behavioral analysis
