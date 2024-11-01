# Introduction to Data Analysis Skills, Roles, and Salaries

The data analysis field is expanding rapidly, with a growing demand for professionals skilled in extracting meaningful insights from complex data. As organizations increasingly rely on data-driven decision-making, roles in data analysis are becoming diverse, ranging from entry-level data analysts to specialized positions like data engineers, data scientists, and machine learning engineers. Each role requires a unique blend of skills, with high demand for core technical proficiencies like Python, SQL, and data visualization tools such as Tableau and Power BI.

Salaries in data analysis vary significantly based on role, experience, and skill set. Foundational roles, like Data Analyst, offer competitive starting salaries, while more specialized roles, such as Data Scientist or Data Engineer, often command higher compensation. Additionally, proficiency in certain high-demand tools and programming languages can significantly impact earning potential, positioning professionals with these skills for rewarding career paths and growth opportunities.

This presentation explores key skills, roles, and salary trends in data analysis to guide aspiring data professionals on the most valuable competencies to develop for a successful and lucrative career in this field.
# The Analysis

## 1. What are the most demanded skills for the top 3 most popular data roles?

To find the most demanded skills for the top 3 most popular data roles, I filtered out those positions by which one were most often listed on job-seeker sites, then filtered for the top skills. The query highlights the job titles, the top skills, and the percentages applicable to the role as listed in the posting. 

## Visualizing the data

## 2. Let's look at some code for visualizing data.

This is the sequence of the code to present the data in the horizontal bar chart with percentages.
```python

    for i, job_title in enumerate(job_titles):
        df_plot = dfj_skills_perc[dfj_skills_perc['job_title_short'] == job_title].head(5)
        sns.barplot(data=df_plot, x='skill_perc', y='job_skills', ax=ax[i], hue='skill_count', palette='dark:b_r')
        ax[i].set_title(job_title)
        ax[i].set_ylabel('')
        ax[i].set_xlabel('')
        ax[i].get_legend().remove()
        ax[i].set_xlim(0, 78)
```

## Results

## 3. The Visual
![Alt text](3_Project/images/skills_demand_top_5_per_role.png)

## Insights

## 4. The Skills and Tools.

- Python is one of the most sought skill for the roles of Data Analysts, Data Engineers, and Data Scientists. 
- SQL is the most requested skill, where in the three roles listed, the percentage is greater than 50%.
- Pandas Library
- matplotlib Library
- Seaborn Library
- Visualizing data through python is accomplished throught the tools of matplotlib and Seaborn. Tableau takes the functionality of those tools  but alamalagates the processing of data into visualizations useful in statistical analysis, and business intelligence. 
-Excel is used in virtually all data analytics professions. Useful for data organization, data analysis,data visualization, and presentations.

## How are in-demand skills trending for Data Analysts

## Visualize the data by useful code.

```python
from matplotlib.ticker import PercentFormatter

dfj_plot = dfj_DA_US_percent.iloc[:, :5]
sns.lineplot(data=dfj_plot, dashes=False, legend='full', palette='tab10')

plt.gca().yaxis.set_major_formatter(PercentFormatter(decimals=0))

plt.show()
```

## The Results Visually
![Alt text](3_Project/images/Top_Skills_Trends.png)

## Insights
- SQL consistently has the highest demand, with over 50% likelihood in job postings. However, there's a gradual decline in demand. This might suggest a slight shift in emphasis or an increase in complementary skills.
- Excel will always maintain a steady demand. However, as noted above, a complementary skill, although this indicates a renewed and steady emphasis on Excel skills.
- Both Python and Tableau show consistent demand. This suggests stable importance for Python programming and data visualization skills in data analyst roles.
- At a 20% avarage throughout the year, with some fluctuations, this suggests Power BI is valued, though not as important as Excel or SQL for data analyst positions.

## 5. How well do the Skills Level correlate to Compensation

## Salary Analysis for Data Analysts

## Visualize the data.
```python
sns.boxplot(data=dfj_US_top6, x='salary_year_avg', y='job_title_short', order=job_order)
sns.set_theme(style='ticks')
# Plot labels
ticks_x = plt.FuncFormatter(lambda y, pos: f'${int(y/1000)}K')
plt.gca().xaxis.set_major_formatter(ticks_x)
plt.show()
```
## Results
![Alt text](3_Project/images/BNW_Roles_Compensation.png)

## Insights
When considering a career in data analysis, potential compensastion for applicable skills utilized, and longevity in the field always appreciated.

The compensation structure across data roles, we observe indicates a logical increase in salaries as experience and role seniority progress. The desired job role does not necessarily guarantee the highest salary.

With Data Analyst as a basis, that average annual compensation is around $85,000. However, some Data Analysts have reported salaries that match or even exceed those of Data Scientists. 

Data Engineer and Senior Data Analyst positions show higher median incomes, though some outliers in compensation align closely with Data Analyst salaries. The higher compensation in these roles also reflects greater experience and the application of more advanced skills, leaning toward development immersion. Interestingly, while Data Analyst roles have lower salaries, they generally involve fewer responsibilities, allowing skill development without as much pressure.

As we move to Data Scientists, the median salary slightly surpasses that of Data Engineers. However, the upper end of compensation for Data Scientists can exceed those in more senior roles, like Senior Data Engineers and Senior Data Scientists, with potential earnings reaching up to $400,000. The median salary of Data Scientists sits around $130,000, a logical progression from Data Analyst roles, aligned with the increased skill requirements.

Overall, median salaries increase with both seniority and specialization, but those positions less often posted, and typically graduated into after time in a lesser position. 

Senior roles, such as Senior Data Scientist and Senior Data Engineer, not only command higher median salaries but also exhibit greater variability in earnings, reflecting the increased responsibilities and compensation diversity at higher experience levels.

## Insights

Data Analyst:

- Average salary: around $85,000.
Variability exists, with some Data Analysts earning on par with Data Scientists, especially if they bring niche skills or work in high-demand industries.
Generally, involves fewer responsibilities, which can be appealing for gaining foundational experience with less pressure.

Data Engineer / Senior Data Analyst:

- Higher median salary than Data Analysts, reflecting more advanced technical skills and responsibilities, often in data architecture or engineering aspects.
Compensation growth aligns with skills like advanced SQL, cloud data storage, and ETL (extract, transform, load) processes.

Data Scientist:

- Median salary: around $130,000.
Upper salary range can reach $400,000 for top-tier professionals, especially those in highly technical or strategic roles.
Data Scientists benefit from the combination of strong analytical skills, coding, and machine learning, and the field offers an appealing career and compensation trajectory.

Senior Roles (Senior Data Scientist, Senior Data Engineer):

- Highest variability in salaries, driven by demand for advanced expertise, leadership responsibilities, and often industry-specific requirements.
Reflects not just seniority but also a diversity in skill sets and roles that companies value differently.

## Data Analyst: The Best Place to Start

Foundational skills in widely used programming languages like Python often offer a better return on investment than niche tools, even if the latter can be valuable in specific roles. Python, as one of the top-paying skills, is versatile across many data and tech roles, making it indispensable, especially when paired with other analytical tools. 

These include technologies like SQL, Tableau, and Power BI also hold significant weight due to their broad applications in data visualization and analysis.

It’s interesting to note the pattern with Microsoft Office tools (Excel, PowerPoint, Word) generally being associated with lower salary ranges compared to more specialized programming and visualization software. While essential, these Office tools may not command the same compensation as skills like Python or SQL, which are critical for more advanced data tasks.

The data suggests a clear action plan: prioritize deepening expertise in Python, SQL, and data visualization tools. These foundational, high-demand skills create a strong basis for many advanced roles and help position you competitively in the job market, both in terms of employability and earning potential.

## The Analysis to Support the Claim

## Visualize the data.

```python
# Top 10 Highest Paid Skills for Data Analysts
sns.barplot(data=dfj_DA_top_pay, x='median', y=dfj_DA_top_pay.index, hue='median', ax=ax[0], palette='dark:b_r')
ax[0].legend().remove()

# Top 10 Most In-Demand Skills for Data Analysts')
sns.barplot(data=dfj_DA_skills, x='median', y=dfj_DA_skills.index, hue='median', ax=ax[1], palette='light:b')
ax[1].legend().remove()
plt.show()
```

![Alt text](3_Project/images/DA_Starting_Pt.png)

## What the Charts indicate.

- Data Analyst Compensation and Skill Optimization
The purpose of this effort is to identify the most lucrative and in-demand skills for data analysts. It builds upon the analysis of skill counts and compensation across a variety of data-related roles. Using Python and visualization libraries, we created comparative graphs to bring clarity to these insights.

Key Insights:

- Data Analyst Positioning: Through our analysis, we now understand how data analysts compare to other data science roles in terms of compensation. While data engineers and scientists typically command higher salaries, data analysts can achieve competitive compensation, particularly when equipped with high-demand, specialized skills.

Compensation by Skill: 

- Our findings indicate that while niche technologies like dplyr, Bitbucket, GitLab, Solidity, Hugging Face, Couchbase, Ansible, MXNet, Cassandra, and VMware offer high compensation, they are generally less in-demand. 
- By contrast, core technologies like Python, Tableau, R, SQL, SAS, Power BI, PowerPoint, Excel, and Word appear frequently in job postings, making them both in-demand and essential for many roles.

Skill Optimization for Data Analysts: Combining our compensation and demand data, we identified that skills such as Python, SQL, Tableau, and Power BI provide an optimal balance of high demand and competitive compensation. While tools like Excel and PowerPoint are still important, more advanced tools tend to offer a better ROI for both career growth and compensation potential.

## Optimal Skills

## Visulize the Data

```python
sns.scatterplot(
    data=dfj_DA_skills_tech,
    x='skill_percent',
    y='median_salary',
    hue='technology'
)
# Adjust text to avoid overlap
adjust_text(texts, arrowprops=dict(arrowstyle='->', color='gray'), expand=(1.2, 1.79))
from matplotlib.ticker import PercentFormatter
ax = plt.gca()
ax.yaxis.set_major_formatter(plt.FuncFormatter(lambda y, pos: f'${int(y/1000)}K'))
ax.xaxis.set_major_formatter(PercentFormatter(decimals=0))

# Adjust layout and display plot 
plt.tight_layout()
plt.show()
```
## Key Insights:
Data Analyst Positioning:
- From our analysis where data analysts’ skills relate to in terms of compensation and job opportunities when equipped with the high-demand skills of Python, SQL, Tableau, and Excel are compensated at higher salaries then less in demand skills.
- From the visualization, in the upper right, programming and analysis tools are most sought after, and generate better salaries. AS stated previously, niche technologies, have their place, and opportunities do exist, by contrast core technologies like Python, Tableau, SQL, Excelappear frequently in job postings, making them both in-demand and essential for many roles.
## The Summary
Data Analysis Career Summary: Skills, Roles, and Salaries Core Skills: Python, SQL, Tableau, Power BI, and Excel are essential for data analysis roles, with Python and SQL standing out for versatility and demand across the industry.
## The Results

![Alt text](3_Project/images/Optimized_Skills.png)

## Roles:
- Data Analyst: Focuses on data interpretation and reporting; serves as an entry point for many data professionals.
- Data Scientist: Incorporates machine learning and advanced analytics, offering higher compensation.
- Data Engineer: Specializes in data infrastructure, with high earning potential due to technical demands.
- Senior Positions: Senior Data Analysts and Data Scientists command higher salaries due to experience and expertise, where some roles surpass $400,000 annually at top levels.
## Salaries:
- Data Analyst: ~$85,000 on average.
- Data Scientist/Data Engineer: ~$130,000 median, reflecting advanced skill requirements.
- Senior roles: Significant salary increases, often with wide variability.
## Conclusion:
Career growth and role advancement are just the start. Do you want more? Prioritize your training in core skills like Python, SQL, and data visualization is essential. These skills provide flexibility and value across roles, especially when progressing toward specialized or senior positions. Those individuals with those skills are sought after in postings and essential across many opportunities.









