# 30113 Final Project: Online Education Participation Analysis Using Large-Scale Data
## Kexin Zhang

### Link to Code:
1. [Part 1 - Data Exploration and Preprocessing.ipynb](https://github.com/macs30113-s24/final-project-kz/blob/main/Part%201%20-%20Data%20Exploration%20and%20Preprocessing.ipynb)
2. [Part 2 - Student Success and Engagement Metrics Calculation.ipynb](https://github.com/macs30113-s24/final-project-kz/blob/main/Part%202%20-%20Student%20Success%20and%20Engagement%20Metrics%20Calculation.ipynb)
3. [Part 3 - In-depth Analysis and Visualization.ipynb](https://github.com/macs30113-s24/final-project-kz/blob/main/Part%203%20-%20In-depth%20Analysis%20and%20Visualization.ipynb)
4. [Part 4 - Model Building and Validation.ipynb](https://github.com/macs30113-s24/final-project-kz/blob/main/Part%204%20-%20Model%20Building%20and%20Validation.ipynb)

### Project Overview
With the rapid transition to digital platforms in education, understanding student engagement and performance in online learning environments has become an esssential area of focus. This project utilizes a large-scale dataset provided by Junyi Academy, a non-profit educational organization based in Taiwan, which consists of over 16 million exercise logs from more than 72,000 students and spans from August 2018 to July 2019. The goal is to use this rich dataset to predict student performance and engagement patterns, facilitating the development of more effective and personalized online learning experiences.

### Research Problem
The central research problem of this project is to analyze and predict student success and engagement in online exercises based on their interaction data. This involves understanding various factors that influence student performance, including grades of students, student demographics, previous performance history, and engagement metrics such as time spent and attempts made per problem.

### Scalable Computing Methods Used
1. **Data Processing at Scale:** Utilized Spark to manage and preprocess large-scale data. The in-memory computation capabilities of Spark were instrumental in speeding up essential data processing tasks, including filtering, aggregation, and merging datasets.
2. **Machine Learning at Scale:** Applied machine learning models using Spark MLlib to analyze student performance. MLlib's reliable and scalable machine learning algorithms facilitated efficient processing of extensive data, improving the predictive analysis.
3. **Distributed Data Storage:** This project did not implement Amazon S3 for data storage as initially planned. Instead, data processing was conducted locally using Spark, which sufficiently supported the project's scale. Future enhancements may include the integration of Amazon S3 to handle larger datasets and facilitate distributed processing.

### Maximizing Research Outcomes with Scalable Computing
Given the extensive volume and granularity of the data involved, traditional data processing methods are insufficient and inefficient. To manage, process, and analyze the vast amount of data effectively and obtain actionable insights within a reasonable timeframe, scalable computing methods are necessary. This project utlizies a variety of scalable computing strategies, ensuring both reliability and efficiency:
1. **Efficient Data Handling:** Utilizing Spark greatly reduced the time required for data preprocessing, enabling rapid handling of over 16 million records. Complex operations such as dataset joins were accelerated, indicating Spark's efficiency in managing large volumes of data.
2. **Accelerated Model Training:** The application of distributed computing via Spark MLlib reduced model training times. This allowed for the parallel training of multiple algorithms, demonstrating the power of scalable methods in speeding up computational tasks.
3. **Real-Time Visualization:** Integration of Spark with visualization tools facilitated immediate data analysis and interactive reporting. This enabled dynamic adjustments based on real-time insights, marking a significant improvement over traditional methods.


### Dataset Description
The dataset includes:
1. `Info_Content.csv`: Metadata about the exercises, including their difficulty level and subject.
2. `Info_UserData.csv`: Demographic and educational background of the students.
3. `Log_Problem.csv`: Records of student problem-solving attempts, including timestamps, correctness, and hints used.

Access the dataset [here](https://www.kaggle.com/datasets/junyiacademy/learning-activity-public-dataset-by-junyi-academy?select=Log_Problem.csv).

### Analysis and Insights
#### Predictive Modeling Techniques
This project uses advanced machine learning techniques within Spark's MLlib to predict student performance on new exercises, utilizing both logistic regression and random forest algorithms. These algorithms are particularly well-suited for handling large datasets:
  - **Logistic Regression:** Helps estimate the probability of a student's success based on historical data, with an emphasis on factors such as time spent on tasks and the number of attempts. This model is cross-validated to ensure robustness and predictive reliability on unseen data.
  - **Random Forest:** Aggregates decisions from multiple decision trees to enhance predictive accuracy and prevent overfitting, making it an effective tool for deriving reliable insights from complex, multifaceted data.

#### Model Performance and Feature Importance
The efficacy of these models is underscored by their high accuracy rates, which were meticulously validated using cross-validation techniques to ensure their generalizability across various datasets:
  - **Logistic Regression:** Achieved an accuracy of approximately 99.65%.
  - **Random Forest:** Demonstrated a similarly high accuracy of about 99.65%.

The models' coefficients provide insights into the influence of each feature on student success:
1. **Total Attempts (Coefficient: -2.197):** Indicates that more attempts per problem generally lead to lower success rates, suggesting areas where students face challenges.
2. **Hints Used (Coefficient: -2.707):** A high usage of hints correlates with lower success rates, pointing to dependencies that may hinder independent problem-solving skills.
3. **Time Spent (Coefficient: 0.0):** Surprisingly, time spent on tasks does not significantly impact success, highlighting that other factors may play a more important role.
  
#### Visualizations and Comparative Analysis
To further elucidate these findings, various visualizations have been created:
1. **Performance by Grade:** Charts that show how average scores are distributed across different grades, providing insights into educational disparities or curriculum effectiveness.
![image](https://github.com/macs30113-s24/final-project-kz/assets/143459510/aef8f80a-147b-47de-821b-db14bdc4235c)
2. **Engagement and Scores Analysis:**  Scatter plots that map the relationship between time spent on tasks and actual scores, revealing patterns in student engagement and learning efficiency.
![image](https://github.com/macs30113-s24/final-project-kz/assets/143459510/5e67643b-dfa2-4cad-8361-56d1b2dd60e0)
3. **Comparative Analysis Across Groups:** Bar charts that compare performance and engagement between self-coached students and those with formal guidance, shedding light on the effectiveness of different learning ways.
![image](https://github.com/macs30113-s24/final-project-kz/assets/143459510/a0c7eb68-2023-416d-99b6-658a5640d9da)

### Project Outcomes and Implications
#### Insights into Key Factors
This analysis has explored critical factors that significantly influence student performance within online learning platforms:
1. **Time Spent on Exercises:** Although time spent did not show a direct correlation with success, its role combined with other factors suggests complex dynamics in learning behaviors.
2. **Number of Attempts:** A higher number of attempts tends to correlate negatively with student success, indicating areas where students struggle and may need additional support.
3. **Hint Usage:** Frequent use of hints is associated with lower performance, suggesting that reliance on aids could be counterproductive without proper guidance.

These insights are vital for understanding and distinguishing behaviors that contribute to or detract from student success in online exercises.

#### Predictive Models for Student Success
The project has successfully developed and validated robust predictive models using logistic regression and random forest techniques:
  - **Logistic Regression** and **Random Forest Models** both achieved an impressive accuracy of approximately 99.65%, demonstrating their effectiveness in forecasting student outcomes. These models are particularly adept at processing large volumes of data to identify underlying patterns that can predict student performance.

#### Actionable Recommendations
Based on the findings, this analysis provides actionable recommendations aimed at educational content developers:
  - **Exercise Structuring:** Suggestions on how to design exercises that engage students effectively, thereby enhancing learning outcomes.
  - **Adaptive Learning Paths:** Emphasizing the importance of adaptive learning environments that can accommodate individual learning styles and paces, ensuring that all students can benefit from personal educational experiences.

These recommendations are intended to help educators and developers optimize online learning platforms, making them more effective and responsive to the diverse needs of students.

### Limitations
There are several limitations to consider:
1. **Data Dependency:** The predictive power of the models is heavily reliant on the quality and breadth of the dataset. The current dataset may not involve all factors that influence student performance, such as external learning activities or personal circumstances.
2. **Scope of Data:** The findings are based on data from a single educational platform, which may limit their applicability to other educational systems. The behaviors and patterns observed may not fully represent those of students in different settings.
3. **Model Generalizability:** While the models achieved high accuracy, their ability to generalize to other datasets is not guaranteed. The specific characteristics of the Junyi Academy dataset could influence the model performance, which may differ when applied to other datasets.

Addressing these limitations in future research could provide more generalized insights, ultimately improving educational strategies and interventions across diverse learning environments.

### Acknowledgments
This project utilizes the Junyi Academy Online Learning Activity Dataset, a comprehensive dataset released by the Junyi Academy Foundation. Junyi Academy, a non-profit organization based in Taiwan, is committed to providing equitable quality education through technological solutions, supporting a wide range of educational research and practical applications. Their dedication to educational equity and data transparency significantly contributes to the advancement of educational technologies and methodologies.
