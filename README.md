## Student Performance Indicator

# This is a Machine Learning End-End Project


# Project Overview

This project develops a predictive model to assess student performance using machine learning regression techniques. Aimed at educational institutions, the model predicts academic outcomes based on students' demographic and academic data. The repository includes a full suite of scripts for data preprocessing, model training, prediction, and evaluation. Additionally, the project is configured for AWS deployment with CI/CD integration, ensuring scalability and ease of updates. This approach enhances decision-making and strategic planning in education by providing actionable insights into student performance.


# EDA-on-Student-Performance-Indicator

## 1. Introduction

### 1) Introduction/Background of the Data

- The dataset used in this project is based on student performance across three key subjects: math, reading, and writing. The data includes a variety of demographic and socio-economic factors such as gender, race/ethnicity, parental level of education, lunch type (standard or free/reduced), and whether the student completed a test preparation course. Each student's performance in the three subjects is recorded, allowing us to explore the relationships between these factors and academic outcomes.

### 2) Why I'm Interested in This Dataset
- Understanding student performance is critical for educators, and parents, as it can help in tailoring interventions to improve educational outcomes. This dataset presents an excellent opportunity to study the intersection of social and demographic factors that influence academic achievement.




### 3) Data Features (Short Explanation)
- Gender: Student's gender (male or female), useful for analyzing gender-based differences in academic performance.

- Race/Ethnicity: Categorical variable representing the student's race/ethnicity (five groups), helps explore racial disparities in performance.

- Parental Education: Highest education level achieved by the student’s parents, ranging from some high school to a master’s degree, which can influence academic outcomes.

- Lunch Type: Indicates whether the student receives a standard or free/reduced lunch, often a proxy for socio-economic status.

- Test Preparation Course: Shows whether a student completed a test preparation course, which is designed to improve academic performance.

- Math Score: Student’s math test score (out of 100), a key metric for evaluating mathematical proficiency.

- Reading Score: Student’s reading test score (out of 100), reflects verbal comprehension skills.

- Writing Score: Student’s writing test score (out of 100), measures writing and expression abilities.


### 4) Data Collection
- Dataset Source - https://www.kaggle.com/datasets/spscientist/students-performance-in-exams?datasetId=74977
- The data consists of 8 columns and 1000 rows.

### 5) Research Objectives
- The main objectives of this research are:

1. To analyze how gender and parental education levels interact to influence performance in math, reading, and writing.
2. To explore the combined impact of lunch type (socio-economic factor) and test preparation (academic intervention) on student performance in math, reading, and writing.
3. To compare and contrast the demographic and socio-economic backgrounds of high and low performers to identify factors that contribute to success or underperformance.
4. To investigate whether test preparation courses have a different impact on academic performance based on gender, race, and parental education.

### 6) Goals
1. To identify whether female and male students benefit equally from higher levels of parental education, and if the effect varies between subjects. This information could help schools and educators design personalized strategies based on gender and family background.
2.To understand whether test preparation courses help level the playing field for students from disadvantaged backgrounds and improve their chances of academic success in all subjects.
3. To help design targeted programs that address the needs of low performers while leveraging the strengths of high performers to maximize academic success for all students.
4. To ensure that test preparation programs are equitable and effective for all students, regardless of their background, and to make improvements if certain groups are not benefiting as much as others.

### EDA Hypotheses (Ask you questions)


1. How does gender combined with parental education influence student performance across different subjects?
- Reason for Interest: Understanding the combined effects of gender and parental education can provide insights into the socio-cultural dynamics that shape academic performance. This question helps identify if parental education has a different impact on male and female students across different subjects, which could help target educational interventions more effectively. 
2. How do lunch type and test preparation course completion together influence performance in math, reading, and writing?
- Reason for Interest: Lunch type is often a proxy for socio-economic status, while test preparation courses are designed to enhance academic performance. Examining how these two factors together influence performance could reveal how well educational interventions (like test prep courses) help bridge socio-economic gaps in student achievement.
3. How do top performers (90th percentile and above) differ from low performers (below 25th percentile) based on gender, parental education, lunch type, and race/ethnicity?
- Reason for Interest: Identifying the key characteristics of both top performers and low performers can help educators and policymakers develop targeted interventions to support struggling students while encouraging high performers. Understanding how socio-economic factors, gender, and race influence these two groups can shed light on existing educational inequalities.
4. How does completing the test preparation course affect performance differently across gender, race, and parental education?
- Reason for Interest: Test preparation courses are intended to enhance academic performance, but the benefits may not be evenly distributed across different groups. Exploring whether the course has a differential impact based on gender, race, or parental education can help assess the equity and effectiveness of such interventions.


## Insights

Question 1: How does gender combined with parental education influence student performance across different subjects?

1. Univariate Analysis Insights:

- Gender Distribution: From the pie chart, the dataset has a slightly higher proportion of female students compared to male students (~51% female, ~49% male).

- Parental Education Level Distribution: The Parental Education Level pie chart shows that the majority of parents have completed high school or some college, with fewer parents holding a bachelor's degree or higher. This suggests that most students come from families where the parental education level is moderate to low.

- Average Score Distribution: The box plot for the average score shows a slightly skewed distribution, with a concentration of students scoring between 60 and 80. There are some outliers at both the high and low ends, indicating variability in performance.

- Subject-Specific Distributions: The histograms for Math, Reading, and Writing Scores show that most students score in the mid-range (60–80). The distribution for writing and reading is slightly more concentrated, whereas math scores show more variability.

2. Bivariate Analysis Insights:

- Pairplot (Gender and Scores): The pairplot with gender shows that female students tend to perform better in reading and writing, while the difference in math performance between males and females is less pronounced. Female students cluster higher in reading and writing scores.
  
- Pairplot (Parental Education Level and Scores): The pairplot shows that students whose parents have a higher education level (bachelor's degree or higher) tend to perform better in all subjects. There is a clear upward shift in the performance of these students compared to those whose parents have a lower level of education.

- Bar Plots (Scores by Gender and Parental Education Level):
>> - Math Scores: Male students have slightly higher math scores on average across most parental education levels, especially at higher parental education levels.
>> - Reading and Writing Scores: Female students outperform male students in both reading and writing across all parental education levels. The effect of parental education is more pronounced in these subjects, where students with more educated parents perform significantly better.
>>  - Overall: The difference in performance between genders is most pronounced in reading and writing, with females consistently scoring higher, while the gap in math is smaller.

3. Multivariate Analysis Insights:

- Heatmap (Gender, Parental Education, and Scores): The heatmap reveals clear trends where students whose parents have higher education levels (e.g., master's degree) tend to perform better across all subjects, regardless of gender. Females consistently score higher in reading and writing, while males perform slightly better in math, especially when their parents have a lower level of education. However, for students whose parents have a higher education level, the performance gap between genders in math diminishes.

- PCA (Projection of Scores by Gender and Parental Education Level): The PCA scatter plot shows distinct clusters based on gender and parental education level. Students with higher parental education levels tend to cluster in the upper regions of the PCA space, indicating higher overall performance in math, reading, and writing. Gender differences are still evident, with female students clustering higher for reading and writing, but the effect of parental education is a stronger determinant of performance across subjects.


Question 2 : How do lunch type and test preparation course completion together influence performance in math, reading, and writing?

1. Univariate Analysis Insights:

- Lunch Type Distribution: The pie chart shows that around 65% of students receive free/reduced lunch, while the remaining 35% receive standard lunch. This indicates a socio-economic divide, with the majority of students coming from lower-income backgrounds.

- Test Preparation Course Completion: About 65% of students did not complete a test preparation course, while 35% did. This suggests that a significant portion of students do not have access to or do not take advantage of test preparation programs.

- Scores Distribution: The box plot for scores shows considerable variability across all subjects. Math scores have a wider range, while reading and writing scores are more concentrated in the 60-80 range, with some outliers.

2. Bivariate Analysis Insights:

- Pairplot (Lunch Type and Scores): Students with standard lunch tend to score higher in math, reading, and writing compared to students with free/reduced lunch. There are clear separations in the clusters, especially in reading and writing. Free/reduced lunch students tend to have lower overall scores, indicating that socio-economic factors (proxied by lunch type) play a significant role in academic performance.

- Pairplot (Test Prep Course Completion and Scores): Students who completed the test preparation course perform better in all subjects, but the effect is more pronounced for math scores.
The reading and writing scores also improve with test preparation, but the difference between those who completed the course and those who didn’t is smaller in these subjects compared to math.

- Bar Plots (Lunch Type and Test Preparation Course):

>> - Math Scores: Students with standard lunch who completed the test preparation course have the highest math scores. The effect of the course is less pronounced for students with free/reduced lunch.
>> - Reading and Writing Scores: The same pattern is observed, with standard lunch students performing better, especially when they have completed the test preparation course.

- Histograms: The histograms reinforce the bar plot insights, showing that students with standard lunch and test prep completion have higher scores. However, the overlap between the groups suggests that test preparation may not fully overcome the impact of socio-economic factors.

3. Multivariate Analysis Insights:
- Heatmap: The heatmap shows that students with standard lunch and test preparation course completion have the highest average scores across math, reading, and writing. In contrast, students with free/reduced lunch who did not complete the test prep course have the lowest scores.
This highlights the combined effect of socio-economic status and test preparation, with socio-economic status playing a dominant role.

- PCA (Projection of Scores): The PCA scatter plot reveals clear clusters based on lunch type and test prep completion. Students with standard lunch and test prep completion cluster towards higher scores in the PCA space, while students with free/reduced lunch and no test prep cluster towards lower scores. The separation of clusters reinforces the idea that both factors—lunch type and test preparation course completion—play significant roles in student performance.




Question 3 : How do top performers (90th percentile and above) differ from low performers (below 25th percentile) based on gender, parental education, lunch type, and race/ethnicity?

1. Univariate Analysis:

- Gender Distribution: The count of males and females is almost evenly distributed between high and low performers. This suggests that gender does not strongly influence whether a student falls into the high or low performer category. Both males and females are equally represented across performance levels.

- Parental Education Level: Students whose parents have higher education (bachelor’s degree or higher) are more likely to be high performers, while students whose parents have only completed high school or some college tend to be low performers. Parental education level plays a critical role in determining student performance, likely due to the support and learning environment provided at home.

- Lunch Type: Students who receive free/reduced lunch (a proxy for lower socio-economic status) are more likely to be low performers. Conversely, students who do not receive free lunch (standard lunch) are more likely to be high performers. Socio-economic factors such as access to resources, which can be inferred from lunch type, are strongly correlated with academic performance.

- Race/Ethnicity: Some race/ethnicity groups show higher representation in either the high or low performer categories, though this varies by group.
There are differences in academic performance across different race/ethnicity groups, which could be influenced by a variety of socio-economic, cultural, and educational factors.


2. Bivariate Analysis:

- Average Scores by Gender and Performance Level: Both male and female students show similar trends, with high performers scoring significantly higher than low performers. Gender alone does not appear to drastically influence performance; the gap between high and low performers is consistent across both genders.

- Average Scores by Parental Education Level and Performance Level: High performers are concentrated among students whose parents have a bachelor’s degree or higher, while low performers are associated with parents who have lower educational attainment. Higher parental education level is a strong predictor of better student performance. This could be due to greater emphasis on academic success, access to resources, or role modeling by parents.

- Average Scores by Lunch Type and Performance Level: Students receiving free/reduced lunch (lower socio-economic status) have significantly lower average scores, while those with standard lunch (higher socio-economic status) tend to be high performers. Socio-economic status, indicated by lunch type, has a clear influence on student performance, with lower-income students more likely to underperform academically.

- Average Scores by Race/Ethnicity and Performance Level: There are variations in performance across different racial/ethnic groups. For instance, certain groups show a higher concentration of high performers, while others have a higher proportion of low performers. Performance levels appear to be influenced by race/ethnicity, likely reflecting broader socio-economic and educational disparities.

3. Multivariate Analysis:

- Multivariate Catplot: The catplot shows that the test preparation course has a noticeable positive impact on students' average scores across gender, parental education, lunch type, and race/ethnicity. Completion of the test preparation course tends to level the playing field across different demographic groups, though some variation still exists due to socio-economic factors.

- FacetGrid for Average Scores by Lunch Type, Gender, Race/Ethnicity, and Parental Education Level: In many instances, students with standard lunch perform better than those receiving free/reduced lunch, especially when comparing across gender and parental education levels. Additionally, higher parental education is consistently linked with better performance, regardless of lunch type or race/ethnicity. This reinforces the idea that socio-economic status (as indicated by lunch type) and parental education are critical factors in determining student success, while gender and race/ethnicity also influence performance to a lesser extent.


Question 4 : How does completing the test preparation course affect performance differently across gender, race, and parental education?

1. Univariate Analysis:

- Gender: The gender distribution is quite balanced with a slight tilt towards female students. This ensures that gender-related analysis is not biased by an underrepresentation of either gender.

- Race/Ethnicity: There are significant differences in the number of students from different racial/ethnic groups. Group C appears to be the most represented, while other groups like Group A and Group E have fewer students. This distribution may affect how race/ethnicity influences performance when combined with other variables.

- Parental Education: The majority of students come from families where the highest level of parental education is some college or a bachelor’s degree. A smaller percentage have parents with graduate-level education. This suggests that a large portion of students might not have access to higher academic support at home, which could influence their overall performance.

- Test Preparation Course: Most students did not complete the test preparation course. This imbalance in completion rates suggests that any observed performance differences will likely highlight the benefits of the course for those who completed it. However, the lower rate of completion should be noted as it limits the sample size for students who completed the course.

2. Bivariate Analysis:

- Average Scores by Gender and Test Preparation Course: Both male and female students who completed the test preparation course tend to score higher, but the increase in performance is more significant among females. The test preparation course positively affects both genders, but there may be additional factors influencing female students to perform better.

- Average Scores by Race/Ethnicity and Test Preparation Course: Different race/ethnicity groups show varying improvements after completing the test preparation course. Some groups benefit significantly more from the course. The test preparation course’s effect varies across racial groups, potentially due to socio-economic factors or differences in learning environments.

- Average Scores by Parental Education Level and Test Preparation Course: Students with parents holding a bachelor's degree or higher show marked improvement after completing the test preparation course, while students with lower parental education levels benefit less. The level of parental education significantly influences how much students benefit from the test preparation course, indicating that higher parental involvement could play a role in enhancing student outcomes.


3. Multivariate Analysis:

- FacetGrid for Test Preparation, Gender, Race, and Parental Education: In the multivariate plot with multiple facets, students who completed the test preparation course consistently score higher across gender, race, and parental education level. However, the degree of improvement varies depending on these factors. This indicates that while the test preparation course is generally effective, its success is influenced by additional socio-demographic variables such as race/ethnicity and parental education.

- Strip Plot with Test Preparation, Gender, and Average Scores by Race/Ethnicity: The strip plot shows the individual performance of students, highlighting outliers and trends in score distribution. It is evident that some students perform exceptionally well or poorly, but completing the test preparation course typically shifts scores upward across most racial/ethnic groups. The test preparation course helps boost scores, but race/ethnicity remains a factor that could influence overall performance. This suggests that targeted interventions might be needed to ensure equitable outcomes.


## References

1. Dataset Source: https://www.kaggle.com/datasets/spscientist/students-performance-in-exams?datasetId=74977
2. EDA Tutorial: https://www.datacamp.com/tutorial/exploratory-data-analysis-python
3. Matplotlib getting started: https://www.w3schools.com/python/matplotlib_getting_started.asp
4. Seaborn plots: https://seaborn.pydata.org/generated/seaborn.catplot.html
5. Pandas Tutorial: https://www.w3schools.com/python/pandas/default.asp
6. Outlier Detection: https://www.scribbr.com/statistics/outliers/


# Independent Features

Below are the Independent Features used in the Model:

1. gender: Student's gender (male or female)
2. race_ethnicity: Group classification (e.g., group D)
3. parental_level_of_education: Highest education level of parents
4. lunch: Type of lunch received (standard or free/reduced)
5. test_preparation_course: Completion status of a preparatory course
6. physics_score: Score in physics subject
7. chemistry_score: Score in chemistry subject


# Algorithms Used:

Model is trained using the below Machine Learning Algorithms and Algorithm giving the highest accuracy is chosen:
1. Linear Regression: Predicts outcomes using linear relationships.
2. Decision Tree: Splits data based on value conditions.
3. Random Forest: Ensemble of decision trees, reduces overfitting.
4. Gradient Boosting: Improves weak models with error-driven updates.
5. AdaBoost: Boosts weak learners into strong ones iteratively.
6. CatBoost: Gradient boosting with categorical data optimization.
7. XGBoost: Optimized gradient boosting with scalability and speed.


# Steps Involved

1. Comprehensive data preprocessing and feature engineering
2. Multiple regression algorithms including Linear Regression, Decision Tree, Random Forest, and Boosting Algorithms.
3. Deployment setup for AWS using CI/CD pipelines.


# Components

1. Data Ingestion is apart of components module which means reading dataset from databases/file locations

2. Ingested data is transformed inside data_transformation.py

3. Model Training will happen in model_trainer.py

4. Model prediction is occuring in predict_pipeline.py

5. Logger has all the log files

6. Exception handling is taking care by exception.py, exc_info() tells the file name and line number where the exception is occuring


# AWS Deployment

1. Utilization of AWS services like IAM, ECR, and EC2.
2. Docker setup on AWS EC2 for container management.
3. GitHub Actions for CI/CD.


# Steps for AWS Deployment

1. Create a user in AWS IAM .
2. Create a repository in AWS Elastic Container Registry.
3. Create an instance in AWS EC2.
4. Setup Docker in AWS EC2 instance.
5. Create Runner in GitHub, execute the commands step by step to  for Download, Configure, Use the self-Hosted Runner.

# Commands for setting up Docker in EC2 :

```
sudo apt-get update -y
```
```
sudo apt-get upgrade
```
```
curl -fsSL https://get.docker.com -o get-docker.sh
```
```
sudo sh get-docker.sh
```
```
sudo usermod -aG docker ubuntu
```
```
newgrp docker

```


# Configure EC2 as self-hosted runner:

Run the commands shown after the runner is created in GitHub for Downloading, Configuring and Running the self-hosted runner


# Setup github secrets:

AWS_ACCESS_KEY_ID=

AWS_SECRET_ACCESS_KEY=

AWS_REGION = us-east-1

AWS_ECR_LOGIN_URI = demo>> 566373416292.dkr.ecr.ap-south-1.amazonaws.com

ECR_REPOSITORY_NAME = simple-app



# Contributing

Contributions to this project are welcome. Please fork the repository and submit a pull request.
