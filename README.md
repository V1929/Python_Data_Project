# The Analysis

## 1. What are the most demanded skills for the top 3 most popular data roles?

To find the most demanded skills for the top 3 most popular data roles, I filtered out those positions by which one were most often listed on job-seeker sites, then filtered for the top skills. The query highlights the job titles, the top skills, and the percentages appicable to the role as listed in the posting. 

View my notebook with details here: [2_Skills_Count.ipynb](3_Project\2_Skills_Count.ipynb)

### Visulaizing the data

## 2. Let's look at some code for visualizing data.

This is the sequunce of the code to present the data in the horizontal bar chart with percentages.


    for i, job_title in enumerate(job_titles):
        df_plot = dfj_skills_perc[dfj_skills_perc['job_title_short'] == job_title].head(5)
        sns.barplot(data=df_plot, x='skill_perc', y='job_skills', ax=ax[i], hue='skill_count', palette='dark:b_r')
        ax[i].set_title(job_title)
        ax[i].set_ylabel('')
        ax[i].set_xlabel('')
        ax[i].get_legend().remove()
        ax[i].set_xlim(0, 78)

### Results

## 3. The Visual
![Visualization of Top Skills for Data Roles](3_Project\images\skills_demand_top_5_per_role.png)

### Insights

## 4. The Skills and Tools.

- Python is one of the most sought skill for the roles of Data Analysts, Data Engineers, and Data Scientists. 
- SQL is the most requested skill, where in the three roles listed, the percentage is greater than 50%.
- Visualizing data through python is accomplished throught the tools of matplotlib and Seaborn. Tableau takes the functionality of those tools  but alamalagates the processing of data into visualizations useful in statistical analysis, and business intelligence. 
-Excel is used in virtually all data analytics professions. Useful for data organization, data analysis,data visualization, and presentations.
