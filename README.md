# AIM: EXPLORING STATISTICAL AND SPECIALIZED DATA VISUALIZATION TECHNIQUES

# THEORY:
In this experiment, libraries like Matplotlib and Seaborn are used to create various plots. These libraries help convert raw numerical data into graphical form,
making it easier to identify patterns, trends, relationships, and outliers.

Two datasets are used in this experiment:
The first dataset contains categorical and numerical values such as Category, Values, Sales, and Profit.
This dataset is used to create basic visualizations like:

1. Area plot
2. Pie chart
3. Donut chart
4. Box plot
5. Heatmap
6. Bubble plot

The second dataset simulates real-world financial data such as Age, Income, Loan Amount, and Credit Score. This dataset is used for:
Outlier detection (Box plot)
Distribution analysis (Histogram)
Multi-variable relationship (Bubble plot)
Correlation analysis (Heatmap)

Different types of plots serve different purposes:

Area plots show trends over categories
Pie/Donut charts represent proportions
Box plots detect outliers
Heatmaps show correlation between variables
Bubble plots represent 3 variables in one graph

Overall, this experiment demonstrates how visualization helps in better data understanding and decision-making.

# Library Import:

import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
import numpy as np

plt → used to create all basic plots

sns → improves visualization + adds statistical features

pd → used to create and manage datasets

np → generates random data and performs calculations

# Random Seed:
np.random.seed(0)

* Fixes random values
* Ensures same output every time code runs
* Important for consistency in experiments

# DataFrame Creation:
df = pd.DataFrame({...})

Converts raw data into table format
Rows = observations
Columns = variables

# Area Plot:
plt.fill_between(df['Category'], df['Values'], color='green', alpha=0.25)

fill_between() → fills area under line
alpha → controls transparency
Used to show trend + magnitude

# Pie Chart:
plt.pie(df['Values'], labels=df['Category'], autopct='%1.2f%%')

Displays proportions

%1.2f%% → shows percentage with 2 decimal places

# Donut Chart:
centre_circle = plt.Circle((0,0), 0.70, fc='white')
fig.gca().add_artist(centre_circle)

Converts pie → donut
Improves readability

# Box Plot:
sns.boxplot(x=df['Values'])

Shows:
Minimum
Q1 (25%)
Median (50%)
Q3 (75%)
Outliers

# Correlation + Heatmap:
corr = df[['Sales','Profit']].corr()
sns.heatmap(corr, annot=True, cmap='coolwarm')
corr() → returns correlation values (-1 to +1)

+1 → strong positive relation
-1 → strong negative relation
0 → no relation

# Bubble Plot:
plt.scatter(df['Sales'], df['Profit'], s=df['Values']*10)

X-axis → Sales
Y-axis → Profit
Size → Values

# Seaborn Scatter:
sns.scatterplot(x='Sales', y='Profit', size='Values', hue='Values', data=df)

size → controls bubble size
hue → adds color dimension

# Histogram:
plt.hist(df1['Credit_Score'], bins=6)

Shows frequency distribution
Helps identify:
Most common values
Spread


# CONCLUSION:
In this experiment, different data visualization techniques were implemented using Matplotlib and Seaborn. 
Various graphs such as area plot, pie chart, box plot, heatmap, and bubble plot were used to analyze the datasets. 
These visualizations helped in understanding data distribution, relationships, and outliers effectively.
Overall, the experiment shows that data visualization makes complex data easier to interpret and supports better analysis and decision-making.
