# 30113 Final Project: Online Education Participation Analysis Using Large-Scale Data
## Kexin Zhang

### Link to Code: [project code.ipynb](https://github.com/macs30113-s24/final-project-kz/blob/main/project%20code.ipynb)

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
Since the dataset is too large to upload on GitHub, I've included a link to the dataset here: [Junyi Academy dataset](https://www.kaggle.com/datasets/junyiacademy/learning-activity-public-dataset-by-junyi-academy?select=Log_Problem.csv)

The dataset comprises three main files:
1. `Info_Content.csv`: Metadata about the exercises, including their difficulty level and subject.
2. `Info_UserData.csv`: Demographic and educational background of the students.
3. `Log_Problem.csv`: Records of student problem-solving attempts, including timestamps, correctness, and hints used.

### Predictive Modeling
The project uses machine learning techniques to predict student performance on new exercises. It utilizes both logistic regression and random forest algorithms within Spark's MLlib, which are particularly suited for handling large datasets. Logistic regression helps estimate the probability of a student's success based on historical data, focusing on factors like time spent on tasks and the number of attempts. Similarly, the random forest model aggregates decisions from multiple decision trees to improve predictive accuracy and prevent overfitting. The logistic regression model is cross-validated to ensure robustness and improve the predictive reliability when applied to unseen data. With the use of this approach, personalized educational strategies may be developed by obtaining a more detailed understanding of the factors that have an important impact on students' outcomes.

### Results and Interpretation

#### Feature Importance:
1. **Total Attempts (Coefficient: -2.197):** More attempts per problem indicate lower chances of success, suggesting students struggle with certain problems.
2. **Hints Used (Coefficient: -2.707):** Higher use of hints correlates with lower success rates, implying dependency on hints is a sign of difficulty.
3. **Time Spent (Coefficient: 0.0):** Time spent per problem does not significantly impact success, suggesting other factors are more crucial.

#### Model Performance:
1. **Coefficients:** The logistic regression model's coefficients reveal the influence of each feature on predicting student success, with the direction and magnitude of impact provided for deeper insights.
2. **Accuracy:** The model's accuracy is evaluated using cross-validation, ensuring robustness and generalizability of the predictive power.
    - **Logistic Regression:** The logistic regression model achieved an accuracy of approximately **99.65%**, indicating a high level of predictive performance. This accuracy was validated using cross-validation techniques to ensure the model's generalizability across different datasets.
    - **Random Forest:** Similarly, the random forest model demonstrated a high accuracy of about **99.65%**. The consistency of this accuracy across different modeling techniques underscores the reliability of the predictive insights generated.
  
#### Visualization (more in code):
1. **Performance by Grade:** Visualizations show how average scores distributed by grade, providing insights into how different groups perform.
![image](https://github.com/macs30113-s24/final-project-kz/assets/143459510/aef8f80a-147b-47de-821b-db14bdc4235c)
2. **Engagement and Scores Analysis:** Scatter plots highlight the relationship between time spent and scores, revealing patterns in student engagement.
![image](https://github.com/macs30113-s24/final-project-kz/assets/143459510/5e67643b-dfa2-4cad-8361-56d1b2dd60e0)
3. **Comparative Analysis Across Groups** Bar charts indicates performance and engagement between self-coached students and those who are not self-coached.
![image](https://github.com/macs30113-s24/final-project-kz/assets/143459510/a0c7eb68-2023-416d-99b6-658a5640d9da)


### Expected Outcomes
The analysis provides:
1. **Insights into Key Factors:** The project identifies detailed insights into factors that significantly impact student performance, such as time spent on exercises, the number of attempts, and hint usage. These insights are crucial for understanding the behaviors associated with higher success rates in online exercises.
2. **Predictive Models for Student Success:** Strong predictive models, including logistic regression and random forest, have been developed to forecast student success in exercises.  These models achieve high accuracy, indicating their effectiveness in predicting outcomes based on students' interaction data.
3. **Actionable Recommendations:** The analysis offers actionable recommendations for educational content developers on how to structure exercises to maximize student engagement and success. This includes emphasizing adaptive learning paths that cater to the diverse needs of students.

### Limitations
There are several limitations to consider:
1. **Data Dependency:** The predictive power of the models is heavily reliant on the quality and breadth of the dataset. The current dataset may not involve all factors that influence student performance, such as external learning activities or personal circumstances.
2. **Scope of Data:** The findings are based on data from a single educational platform, which may limit their applicability to other educational systems. The behaviors and patterns observed may not fully represent those of students in different settings.
3. **Model Generalizability:** While the models achieved high accuracy, their ability to generalize to other datasets is not guaranteed. The specific characteristics of the Junyi Academy dataset could influence the model performance, which may differ when applied to other datasets.

### Acknowledgments
This project utilizes the Junyi Academy Online Learning Activity Dataset, a comprehensive dataset released by the Junyi Academy Foundation. Junyi Academy, a non-profit organization based in Taiwan, is committed to providing equitable quality education through technological solutions, supporting a wide range of educational research and practical applications. Their dedication to educational equity and data transparency significantly contributes to the advancement of educational technologies and methodologies.
