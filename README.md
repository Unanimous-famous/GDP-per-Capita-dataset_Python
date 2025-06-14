# GDP per Capita Analysis with Python 🧮


This project explores GDP (nominal) per capita estimates from three global organizations: the **IMF**, **UN**, and **World Bank**. It uses Python for data analysis and visualization with Pandas, Seaborn, and Matplotlib.

## 📁 Dataset

The dataset is in CSV format and includes nominal GDP per capita estimates by country.

Key columns:
- `Country`
- `IMF_Estimate`
- `UN_Estimate`
- `WorldBank_Estimate`
- `UN_Region`

---

## 🧹 Data Cleaning & Overview

### 1. Initial Exploration

```python
df.head()
```

![image](https://github.com/user-attachments/assets/ee4fa917-56b2-423a-ac20-456957c696b3)

### 2. Descriptive Statistics

```python
df.describe()
```

![image](https://github.com/user-attachments/assets/ee4fa917-56b2-423a-ac20-456957c696b3)

---

## 📊 Visualizations

### 3. Histogram of GDP Estimates

```python
df[["IMF_Estimate", "UN_Estimate", "WorldBank_Estimate"]].hist(figsize=(12, 9))
```

![image](https://github.com/user-attachments/assets/109f4e89-2819-424e-bc3a-d8e68b62c302)

### 4. GDP by UN Region (Seaborn Bar Plot)

```python
sns.barplot(x="UN_Region", y="IMF_Estimate", data=df)
```

![image](https://github.com/user-attachments/assets/109f4e89-2819-424e-bc3a-d8e68b62c302)

---

### 5. Correlation Matrix (Heatmap)
```python
sns.heatmap(df[["IMF_Estimate", "UN_Estimate", "WorldBank_Estimate"]].corr(), annot=True, cmap="Purples")
```

![image](https://github.com/user-attachments/assets/c134f8a5-a42d-41b6-a979-ec349923e9c5)



### 6. 📊 Bar Plots – GDP per Capita by UN Region

To compare GDP estimates across UN regions, we used Seaborn's `barplot` to generate horizontal and vertical bar charts for each data source.

```python
sns.barplot(x="UN_Region", y="WorldBank_Estimate", data=df, errorbar=None)
plt.show()
```

```python
sns.barplot(x="WorldBank_Estimate", y="UN_Region", data=df, errorbar=None)
plt.show()
```

```python
fig = plt.figure(figsize=(8, 5))
ax = sns.barplot(x="IMF_Estimate", y="UN_Region", data=df, errorbar=None)
ax.bar_label(ax.containers[0])
plt.show()
```

```python
fig = plt.figure(figsize=(8, 5))
ax = sns.barplot(x="UN_Region", y="IMF_Estimate", data=df, errorbar=None)
ax.bar_label(ax.containers[0])
ax.set_title("Regions by IMF Estimate")
plt.show()
```

![image](https://github.com/user-attachments/assets/803d4419-d70b-4c91-ba9e-06f28fc2ca9a)



These plots help visualise the variation in GDP estimates depending on the source, and provide insights into regional economic disparities.



### 7. 📊 Recreating and Comparing Bar Plots Across Libraries

To evaluate and showcase the unique strengths of the three major Python visualisation libraries—**Matplotlib**, **Seaborn**, and **Plotly**—we begin by recreating the same bar chart (average GDP per UN region from the World Bank) using each one. Then, we highlight **three unique visualisations per library**, designed to showcase their distinctive capabilities or ease of use.

### 🔁 Recreating the Same Plot: Average WorldBank GDP per UN Region





# GDP per Capita Analysis with Python 🧮

This project explores GDP (nominal) per capita estimates from three global organizations: the **IMF**, **UN**, and **World Bank**. It uses Python for data analysis and visualization with Pandas, Seaborn, and Matplotlib.

## 📁 Dataset

The dataset is in CSV format and includes nominal GDP per capita estimates by country.

Key columns:
- `Country`
- `IMF_Estimate`
- `UN_Estimate`
- `WorldBank_Estimate`
- `UN_Region`

---

## 🧹 Data Cleaning & Overview

### Initial Exploration
```python
df.head()
```

![image](https://github.com/user-attachments/assets/ee4fa917-56b2-423a-ac20-456957c696b3)

### Descriptive Statistics
```python
df.describe()
```

![image](https://github.com/user-attachments/assets/ee4fa917-56b2-423a-ac20-456957c696b3)

---

## 📊 Visualizations

### Histogram of GDP Estimates
```python
df[["IMF_Estimate", "UN_Estimate", "WorldBank_Estimate"]].hist(figsize=(12, 9))
```

![image](https://github.com/user-attachments/assets/109f4e89-2819-424e-bc3a-d8e68b62c302)

### GDP by UN Region (Seaborn Bar Plot)
```python
sns.barplot(x="UN_Region", y="IMF_Estimate", data=df)
```

![image](https://github.com/user-attachments/assets/109f4e89-2819-424e-bc3a-d8e68b62c302)

### Correlation Matrix (Heatmap)
```python
sns.heatmap(df[["IMF_Estimate", "UN_Estimate", "WorldBank_Estimate"]].corr(), annot=True, cmap="Purples")
```

![image](https://github.com/user-attachments/assets/c134f8a5-a42d-41b6-a979-ec349923e9c5)

### Bar Plots – GDP per Capita by UN Region
```python
sns.barplot(x="UN_Region", y="WorldBank_Estimate", data=df, errorbar=None)
plt.show()
```

```python
sns.barplot(x="WorldBank_Estimate", y="UN_Region", data=df, errorbar=None)
plt.show()
```

```python
fig = plt.figure(figsize=(8, 5))
ax = sns.barplot(x="IMF_Estimate", y="UN_Region", data=df, errorbar=None)
ax.bar_label(ax.containers[0])
plt.show()
```

```python
fig = plt.figure(figsize=(8, 5))
ax = sns.barplot(x="UN_Region", y="IMF_Estimate", data=df, errorbar=None)
ax.bar_label(ax.containers[0])
ax.set_title("Regions by IMF Estimate")
plt.show()
```

![image](https://github.com/user-attachments/assets/803d4419-d70b-4c91-ba9e-06f28fc2ca9a)

These plots help visualise the variation in GDP estimates depending on the source, and provide insights into regional economic disparities.

---

## 📊 Recreating and Comparing Bar Plots Across Libraries

To evaluate and showcase the unique strengths of the three major Python visualisation libraries—**Matplotlib**, **Seaborn**, and **Plotly**—we begin by recreating the same bar chart (average GDP per UN region from the World Bank) using each one. Then, we highlight **three unique visualisations per library**, designed to showcase their distinctive capabilities or ease of use.

### 🔁 Recreating the Same Plot: Average WorldBank GDP per UN Region

#### Using Matplotlib
```python
plt.figure(figsize=(10, 8))
region_worldbank_avg = df.groupby("UN_Region")["WorldBank_Estimate"].mean().sort_values()
plt.bar(region_worldbank_avg.index, region_worldbank_avg.values)
plt.xticks(rotation=90)
plt.xlabel("UN Region")
plt.ylabel("Average WorldBank Estimate")
plt.title("Average WorldBank Estimate per UN Region (Matplotlib)")
plt.tight_layout()
plt.show()
```
![image](https://github.com/user-attachments/assets/04ac93d5-8ab4-42f8-bd83-4ae54d21414b)


#### Using Plotly (graph_objects)
```python
import plotly.graph_objects as go
region_worldbank_avg = df.groupby("UN_Region")["WorldBank_Estimate"].mean().sort_values()
fig = go.Figure(data=[go.Bar(x=region_worldbank_avg.index, y=region_worldbank_avg.values)])
fig.update_layout(
    title="Average WorldBank Estimate per UN Region (Plotly)",
    xaxis_title="UN Region",
    yaxis_title="Average WorldBank Estimate",
    xaxis={'categoryorder':'total ascending'}
)
fig.show()
```
![image](https://github.com/user-attachments/assets/e3855ca3-bf3f-41b5-ac8d-ff36041b1cf2)


#### Using Seaborn
```python
plt.figure(figsize=(10, 8))
sns.barplot(
    x="UN_Region",
    y="WorldBank_Estimate",
    data=df,
    errorbar=None,
    order=df.groupby("UN_Region")["WorldBank_Estimate"].mean().sort_values().index
)
plt.xticks(rotation=90)
plt.xlabel("UN Region")
plt.ylabel("Average WorldBank Estimate")
plt.title("Average WorldBank Estimate per UN Region (Seaborn)")
plt.tight_layout()
plt.show()
```
![image](https://github.com/user-attachments/assets/3353d255-f26d-4d93-a9a6-c6e74b154cbf)

These three charts help illustrate the **basic differences in syntax and styling** across libraries:
- **Matplotlib** offers low-level control.
- **Plotly** brings interactivity and better layout responsiveness.
- **Seaborn** provides clean, high-level APIs for statistical plots.

---

## 🔍 Unique Visualisations Showcasing Each Library's Strengths

Below are three **"native-style" or uniquely convenient** plots per library, showcasing built-in functionality not as cleanly replicated by the others.

---

### 🎯 Matplotlib – Fine Control and Core Plotting

#### 1. Scatter Plot by Region (Custom Markers)
```python
plt.figure(figsize=(12, 8))
for region in df['UN_Region'].unique():
    subset = df[df['UN_Region'] == region]
    plt.scatter(subset['IMF_Estimate'], subset['WorldBank_Estimate'], label=region, alpha=0.6)
plt.xlabel("IMF Estimate")
plt.ylabel("WorldBank Estimate")
plt.title("IMF vs WorldBank Estimate by UN Region (Matplotlib Scatter)")
plt.legend(bbox_to_anchor=(1.05, 1), loc='upper left')
plt.tight_layout()
plt.show()
```
![image](https://github.com/user-attachments/assets/94999cdf-9016-4129-adb1-a5a245590ca1)

#### 2. Pie Chart of Countries per Region
```python
region_counts = df['UN_Region'].value_counts()
plt.figure(figsize=(10, 10))
plt.pie(region_counts, labels=region_counts.index, autopct='%1.1f%%', startangle=90)
plt.title("Distribution of Countries by UN Region (Matplotlib Pie Chart)")
plt.axis('equal')
plt.show()
```
![image](https://github.com/user-attachments/assets/05a2a656-c92b-402c-8da3-2dc2063925a7)

#### 3. Box Plot with Grouped Data
```python
plt.figure(figsize=(12, 8))
df.boxplot(column='WorldBank_Estimate', by='UN_Region', vert=False)
plt.title("Distribution of WorldBank Estimates per UN Region (Matplotlib Box Plot)")
plt.xlabel("WorldBank Estimate")
plt.ylabel("UN Region")
plt.suptitle('')
plt.tight_layout()
plt.show()
```
![image](https://github.com/user-attachments/assets/2e0fc0f9-ab45-4ba0-ab97-a051d995af09)

---

### 🧠 Plotly – Interactivity & Rich Hierarchies

#### 1. Interactive Scatter with Hover Text
```python
fig = go.Figure()
for region in df['UN_Region'].unique():
    subset = df[df['UN_Region'] == region]
    fig.add_trace(go.Scatter(
        x=subset['IMF_Estimate'],
        y=subset['WorldBank_Estimate'],
        mode='markers',
        name=region,
        text=subset['Country/Territory'],
        hoverinfo='text+x+y'
    ))
fig.update_layout(
    title="IMF vs WorldBank Estimate by UN Region (Plotly Interactive Scatter)",
    xaxis_title="IMF Estimate",
    yaxis_title="WorldBank Estimate"
)
fig.show()
```



https://github.com/user-attachments/assets/4235cd84-5187-4c67-99c4-9ed33c5bd05e




#### 2. Sunburst Chart (Hierarchy Visual)
```python
region_sum_imf = df.groupby('UN_Region')['IMF_Estimate'].sum().reset_index()
fig = go.Figure(go.Sunburst(
    labels=region_sum_imf['UN_Region'],
    parents=['' for _ in region_sum_imf['UN_Region']],
    values=region_sum_imf['IMF_Estimate'],
    hovertemplate='Region: %{label}<br>Total IMF Estimate: %{value}<extra></extra>'
))
fig.update_layout(margin=dict(t=0, l=0, r=0, b=0), title_text='Total IMF Estimate by UN Region (Plotly Sunburst - Simplified)')
fig.show()
```


https://github.com/user-attachments/assets/aaa487ff-f0b9-4a7a-b785-ae196deba5d7



#### 3. 3D Scatter Plot (IMF vs WorldBank vs UN)
```python
fig = go.Figure(data=[go.Scatter3d(
    x=df['IMF_Estimate'],
    y=df['WorldBank_Estimate'],
    z=df['UN_Estimate'],
    mode='markers',
    marker=dict(
        size=5,
        color=df['UN_Estimate'],
        colorscale='Viridis',
        opacity=0.8
    ),
    text=df['Country/Territory'],
    hoverinfo='text+x+y+z'
)])
fig.update_layout(
    title="IMF, WorldBank, and UN Estimates (Plotly 3D Scatter)",
    scene=dict(
        xaxis_title='IMF Estimate',
        yaxis_title='WorldBank Estimate',
        zaxis_title='UN Estimate'
    )
)
fig.show()
```


https://github.com/user-attachments/assets/5270d5e8-da9e-469b-83be-adedcea57e30


---

### 🧪 Seaborn – Statistical Distributions & Matrix Plots

#### 1. Violin Plot (Distribution Shape)
```python
plt.figure(figsize=(12, 8))
sns.violinplot(x='WorldBank_Estimate', y='UN_Region', data=df, inner='quartile')
plt.title("Distribution Shape of WorldBank Estimates per UN Region (Seaborn Violin Plot)")
plt.xlabel("WorldBank Estimate")
plt.ylabel("UN Region")
plt.tight_layout()
plt.show()
```
![image](https://github.com/user-attachments/assets/08ed954d-2346-49d9-9d82-cb562683d499)

#### 2. Joint Plot with Hexbins & Regression
```python
sns.jointplot(x='IMF_Estimate', y='WorldBank_Estimate', data=df, kind='hex')
plt.suptitle("Relationship between IMF and WorldBank Estimates (Seaborn Joint Plot - Hex)", y=1.02)
plt.show()

sns.jointplot(x='IMF_Estimate', y='WorldBank_Estimate', data=df, kind='reg')
plt.suptitle("Relationship between IMF and WorldBank Estimates (Seaborn Joint Plot - Regression)", y=1.02)
plt.show()
```
![image](https://github.com/user-attachments/assets/abf25bf9-eb02-4350-8577-423fe393545d)

![image](https://github.com/user-attachments/assets/f18a4037-5802-456e-babd-21e74dcbbf61)

#### 3. Pair Plot of All Estimate Columns
```python
numerical_cols = ["IMF_Estimate", "WorldBank_Estimate", "UN_Estimate"]
sns.pairplot(df[numerical_cols], diag_kind='kde')
plt.suptitle("Pairwise Relationships and Distributions of Estimates (Seaborn Pair Plot)", y=1.02)
plt.show()
```
![image](https://github.com/user-attachments/assets/7b163216-c079-4335-837a-82251ba3fbf0)

---

## 🧩 Summary of Library Strengths

| Library     | Strengths                                                                 |
|-------------|--------------------------------------------------------------------------|
| **Matplotlib** | Core plotting flexibility, full control over all elements, publication-quality static plots |
| **Seaborn**    | Statistical and distribution-focused visuals with easy grouping logic |
| **Plotly**     | Interactivity, web-friendly layouts, and advanced charts (Sunburst, 3D) |

This comparison helps understand not just how to create visualisations, but **why you might choose a particular library** depending on your goals—whether it’s interactivity, statistical interpretation, or fine-grained visual control.


---

## 🔍 Removing Outliers using IQR Method

To ensure that our analysis is not skewed by extreme values, we apply the **Interquartile Range (IQR) method** to filter out outliers from the `UN_Estimate` column.

```python
lower_q = df["UN_Estimate"].quantile(0.25)
higher_q = df["UN_Estimate"].quantile(0.75)
iqr = higher_q - lower_q

upper_boundary = higher_q + 1.5 * iqr
lower_boundary = lower_q - 1.5 * iqr

df_filtered = df[(df["UN_Estimate"] < upper_boundary) & (df["UN_Estimate"] > lower_boundary)]
```

We then compare the shape of the filtered and original dataframes to assess the impact:

```python
df.shape         # (223, ...)
df_filtered.shape # (196, ...)
```

👉 **27 rows** (≈12%) were identified as outliers based on UN estimates and dropped from the dataset.

---

## 📐 Mean Comparison: With vs Without Outliers

To understand the impact of outliers, we compute the **mean GDP per capita** from each source before and after filtering:

```python
# UN
df_filtered.UN_Estimate.mean()
df.UN_Estimate.mean()

# World Bank
df_filtered.WorldBank_Estimate.mean()
df.WorldBank_Estimate.mean()

# IMF
df_filtered.IMF_Estimate.mean()
df.IMF_Estimate.mean()
```

We can summarise this in a simple comparison table:

| Estimate Source | Mean (Original Data) | Mean (Without Outliers) |
|------------------|----------------------|--------------------------|
| **UN**           | `df.UN_Estimate.mean()` → *e.g., 17,289* | `df_filtered.UN_Estimate.mean()` → *e.g., 14,755* |
| **World Bank**   | `df.WorldBank_Estimate.mean()` → *e.g., 19,004* | `df_filtered.WorldBank_Estimate.mean()` → *e.g., 15,281* |
| **IMF**          | `df.IMF_Estimate.mean()` → *e.g., 18,250* | `df_filtered.IMF_Estimate.mean()` → *e.g., 14,912* |

This comparison highlights the **inflationary effect of extreme values** on global GDP per capita estimates, and shows the importance of outlier treatment in statistical analysis.


## 📈 Interactive Visualisations with Plotly Express

This section reproduces the most insightful visuals using **Plotly Express**, along with a few advanced chart types that highlight relationships between population estimates. These interactive charts enhance exploratory analysis and provide deeper insights.

---

### 🔹 Box Plots for Individual Estimates

Box plots summarise the distribution of population estimates from different sources. These visuals help detect outliers and compare medians, quartiles, and variability.

```python
# Box plot of UN_Estimate (filtered data)
fig = px.box(df_filtered, y="UN_Estimate", title='Box Plot of Filtered UN Estimate')
fig.show()

# Box plot of WorldBank_Estimate (filtered data)
fig = px.box(df_filtered, y="WorldBank_Estimate", title='Box Plot of Filtered WorldBank Estimate')
fig.show()

# Box plot of IMF_Estimate (filtered data)
fig = px.box(df_filtered, y="IMF_Estimate", title='Box Plot of Filtered IMF Estimate')
fig.show()
````



https://github.com/user-attachments/assets/0c10ea8e-fbb8-4254-8c04-b2f90cdf1da6

---


### 🔹 Scatter Plots for Cross-Comparison

Scatter plots visualise the relationship and correlation between estimates from different sources.

```python
# Scatter plot of UN_Estimate vs WorldBank_Estimate
fig = px.scatter(df_filtered, x="UN_Estimate", y="WorldBank_Estimate",
                 title='UN Estimate vs WorldBank Estimate',
                 hover_name="Country/Territory")
fig.show()

# Scatter plot of UN_Estimate vs IMF_Estimate
fig = px.scatter(df_filtered, x="UN_Estimate", y="IMF_Estimate",
                 title='UN Estimate vs IMF Estimate',
                 hover_name="Country/Territory")
fig.show()

# Scatter plot of WorldBank_Estimate vs IMF_Estimate
fig = px.scatter(df_filtered, x="WorldBank_Estimate", y="IMF_Estimate",
                 title='WorldBank Estimate vs IMF Estimate',
                 hover_name="Country/Territory")
fig.show()
```



https://github.com/user-attachments/assets/8127d731-ef09-4890-ae2b-8b7de3e29996



---

### 🔹 Combined Box Plot of All Estimates

To compare the three estimates side-by-side, we melt the data into long format and plot a unified box plot.

```python
# Melted DataFrame for combined box plot
df_melted = df_filtered.melt(value_vars=["UN_Estimate", "WorldBank_Estimate", "IMF_Estimate"],
                             var_name="Estimate Type", value_name="Estimate Value")

# Combined box plot
fig = px.box(df_melted, x="Estimate Type", y="Estimate Value",
             title='Box Plot of Different Estimate Types (Filtered Data)')
fig.show()
```

![image](https://github.com/user-attachments/assets/bc50ad9d-a738-483f-b9ad-d384a477aa52)


---

### 🔹 Violin Plot for Distribution Shape

Violin plots provide a richer view of distribution compared to box plots by showing the density of values at different levels.

```python
# Violin plot of UN_Estimate
fig = px.violin(df_filtered, y="UN_Estimate", box=True, points="all",
                title='Violin Plot of Filtered UN Estimate')
fig.show()
```

https://github.com/user-attachments/assets/01934cde-0fe2-4073-affa-a21066c7afdc

---

### 🌞 Sunburst Chart by Region and Country

Sunburst charts display hierarchical relationships using radial space. A dummy 'Region' column was created for grouping countries.

```python
# Add dummy Region column
df_filtered['Region'] = np.random.choice(['Asia', 'Europe', 'Americas', 'Africa', 'Oceania'], size=len(df_filtered))

# Sunburst chart of UN estimates
fig = px.sunburst(df_filtered, path=['Region', 'Country/Territory'], values='UN_Estimate',
                  title='Sunburst Chart of UN Estimate by Region and Country')
fig.show()
```

https://github.com/user-attachments/assets/5f68ee2d-f539-49ae-bea2-b60eeba1e675

---

### 🔥 Density Heatmap

Density heatmaps are useful for visualising concentration and distribution patterns across two quantitative variables.

https://github.com/user-attachments/assets/1090e6b0-7789-48aa-bfb4-b04416ecabfe

---

🧩 **Note:** If you encounter any import errors, make sure `plotly` is installed:

```bash
pip install plotly
```

### 3D Scatter Plot by Region

This interactive 3D scatter plot visualizes the relationship between population estimates from the UN, World Bank, and IMF for various countries. Each point represents a country, with colors indicating the region it belongs to. The axes correspond to the three different population estimates, allowing easy comparison across data sources and geographic regions.


https://github.com/user-attachments/assets/718602a3-43d6-4d6d-bf95-ecf95c64f585


---

### Bubble Chart Comparing UN and World Bank Estimates

The bubble chart shows the relationship between UN and World Bank population estimates for different countries. Each bubble represents a country, where the bubble size corresponds to the IMF estimate, and the bubble color shows the region. This visualization helps reveal correlations and differences between data sources while highlighting regional patterns.



https://github.com/user-attachments/assets/39b60414-ad17-4661-a2b9-fa865e224cc5


---

### Parallel Categories Plot of Estimate Categories by Region

This plot categorizes the population estimates into defined ranges (e.g., Very Low, Low, Medium, High, Very High) and visualizes how countries are distributed across these categories for each estimate source. The plot includes the region dimension to show patterns and relationships in the population estimate categories by geographic area.


https://github.com/user-attachments/assets/3a54a3ac-e273-4e82-bd1b-94cb5124ba45

---

### Gantt-like Chart of Estimate Ranges for Selected Countries

This chart visualizes the range between the minimum and maximum population estimates reported by the UN, World Bank, and IMF for the top 20 countries with the largest discrepancies among these sources.

- Each horizontal line represents a country, stretching from its lowest estimate to its highest estimate.
- The length of the line indicates the magnitude of disagreement or uncertainty among the three data sources.
- Countries with the widest ranges suggest substantial variability or data inconsistency in population figures.
- This visualization helps identify which countries have the greatest divergence in population estimates, highlighting where further investigation or data reconciliation may be needed.


https://github.com/user-attachments/assets/6378748a-d47c-4432-a11c-e5e9bcafca7f


*Interpretation tip:*  
Countries with narrow ranges show strong agreement between sources, while wide ranges may reflect data collection challenges or differing methodologies.

---

### Boxplots of IMF, World Bank, and UN Estimates

Boxplots provide a statistical summary of the distribution of population estimates from each source across all countries:

- The boxes show the interquartile range (middle 50% of values), with the median line inside each box.
- Whiskers extend to show the range of typical data, while dots mark outliers.
- Comparing the three boxplots reveals differences in the central tendency and variability of estimates among the IMF, World Bank, and UN.
- Outliers indicate countries where an estimate is significantly different from the typical range.


https://github.com/user-attachments/assets/f271edea-562a-4953-aa19-c5646f3106af


*Interpretation tip:*  
This overview helps to quickly assess which source tends to report higher or more variable estimates, and where unusual data points exist that might require closer scrutiny.

---

### Choropleth Map of IMF Estimates by Country

This world map colors countries based on their IMF population estimates.

- Countries are shaded from low to high values using a Viridis color scale.
- Hover to see exact IMF estimates for each country.
- Useful for geographical comparison of population estimates.


https://github.com/user-attachments/assets/df2665f2-b6ef-4095-840d-b286625d3c6b


*Note:* Country names in the data must match Plotly’s recognized names or use ISO codes for accurate mapping. This is not apparently the case for a few, for instance, the United States.



---

### Scatter Map of World Bank Estimates by Country and Region

This map plots countries as points based on latitude and longitude, sized by World Bank population estimates and colored by region.

- Larger points indicate higher estimates.
- Hover over points to see country names and exact estimates.
- Offers spatial insight into population estimate distribution and regional patterns.

![image](https://github.com/user-attachments/assets/8603ef1e-28f8-443a-9f99-f08566d32812)


*Note:* Latitude and longitude data are required for this visualization. As it was not the case, it does not work properly, but is introduced for the relevant use cases.


---

### Violin Plots of Population Estimates by Region

These violin plots visualize the distribution of population estimates (IMF, World Bank, and UN) grouped by region.

- Each violin shape shows the density of estimate values within each region.
- Inner box plots and outlier points highlight data spread and variability.
- Useful for comparing how estimate distributions differ across regions and organizations.


https://github.com/user-attachments/assets/e29c6afb-37fe-439b-9721-6786bbfa2ed5


---

*Common Tips for These Visualizations:*

- Ensure categorical columns are truly categorical for color/grouping variables.
- Check numerical columns for missing or invalid values.
- Verify geographical data matches expected formats when using maps.
- Adjust bin ranges or labels in the parallel categories plot to fit your data’s scale.

---

## Conclusion

This project demonstrates how diverse visualization techniques can be applied to explore and analyze population estimate data from multiple global organizations, including the IMF, World Bank, and UN. Through a variety of interactive and static plots — from heatmaps and correlation matrices to parallel categories plots and geographic maps — we gain valuable insights into:

- Regional differences and similarities in population estimates,
- The degree of agreement between organizations,
- Patterns and distributions within and across continents,
- And spatial relationships revealed through maps.

These visualizations not only help uncover trends and anomalies in the data but also showcase the power of Python libraries like Plotly and Pandas for interactive data exploration.

By integrating multiple perspectives and representations, this approach supports better understanding and informed decision-making when working with complex international datasets.

Feel free to explore the notebook/code further, adapt the visualizations to your own datasets, and extend the analysis with additional data or custom features.

---

## 🚀 Skills Demonstrated

✅ Data wrangling and aggregation with **pandas**  
✅ Numerical and categorical data binning  
✅ Interactive and static data visualization with **Plotly Express** and **Plotly Graph Objects**  
✅ Creating heatmaps, correlation matrices, parallel categories plots, choropleth maps, scatter geo maps, and violin plots  
✅ Handling geospatial data and map projections  
✅ Data storytelling through comprehensive multi-visual approaches  

---

## 💡 Future Improvements

- Add more robust **error handling** and data validation steps  
- Incorporate **real country ISO codes** for improved mapping accuracy  
- Expand dataset with additional socio-economic or demographic indicators  
- Develop a **dashboard** interface using Plotly Dash or Streamlit for dynamic user interaction  
- Automate report generation and export with Jupyter Notebooks and **nbconvert**  
- Integrate time series analysis if temporal data becomes available  

---

Thank you for reviewing this project!

