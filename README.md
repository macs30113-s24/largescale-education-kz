# 30113 Final Project: Online Education Participation Analysis Using Large-Scale Data

### Project Overview

With the rapid transition to digital platforms in education, understanding student engagement and performance in online learning environments has become an esssential area of focus. This project utilizes a large-scale dataset provided by Junyi Academy, a non-profit educational organization based in Taiwan, which consists of over 16 million exercise logs from more than 72,000 students and spans from August 2018 to July 2019. The goal is to use this rich dataset to predict student performance and engagement patterns, facilitating the development of more effective and personalized online learning experiences.

### Research Problem

The central research problem of this project is to analyze and predict student success and engagement in online exercises based on their interaction data. This involves understanding various factors that influence student performance, including grades of students, student demographics, previous performance history, and engagement metrics such as time spent and attempts made per problem.

### Importance of Scalable Computing

Given the extensive volume and granularity of the data involved, traditional data processing methods are insufficient and inefficient. In order to manage, process, and analyze the vast amount of data in an effective way and obtain actionable insights within a reasonable timeframe, scalable computing methods are necessary. This project uses a variety of scalable computing strategies, such as parallel data processing and machine learning algorithms optimized for large datasets, to make sure that the analysis is both reliable and efficient.

### Scalable Computing Methods Used

1. **Data Processing at Scale:** Utilized Spark to manage and preprocess large-scale data. The in-memory computation capabilities of Spark were instrumental in speeding up essential data processing tasks, including filtering, aggregation, and merging datasets.
2. **Machine Learning at Scale:** Applied machine learning models using Spark MLlib to analyze student performance. MLlib's reliable and scalable machine learning algorithms facilitated efficient processing of extensive data, enhancing the predictive analysis.
3. **Distributed Data Storage:** This project did not implement Amazon S3 for data storage as initially planned. Instead, data processing was conducted locally using Spark, which sufficiently supported the project's scale. Future enhancements may include the integration of Amazon S3 to handle larger datasets and facilitate distributed processing.
4. **Visualization and Reporting:** Interactive visualizations were created using libraries such as Matplotlib and Seaborn within the local development environment. While AWS was not utilized for hosting these visualizations, this approach allowed for effective analysis and representation of data trends and patterns.

### Dataset Description

The dataset comprises three main files:
1. Info_Content.csv: Metadata about the exercises, including their difficulty level and subject.
2. Info_UserData.csv: Demographic and educational background of the students.
3. Log_Problem.csv: Records of student problem-solving attempts, including timestamps, correctness, and hints used.

### Predictive Modeling

The project uses machine learning techniques to predict student performance on new exercises. It utilizes both logistic regression and random forest algorithms within Spark's MLlib, which are particularly suited for handling large datasets. Logistic regression helps estimate the probability of a student's success based on historical data, focusing on factors like time spent on tasks and the number of attempts. Similarly, the random forest model aggregates decisions from multiple decision trees to improve predictive accuracy and prevent overfitting. The logistic regression model is cross-validated to ensure robustness and improve the predictive reliability when applied to unseen data. With the use of this approach, personalized educational strategies may be developed by obtaining a more detailed understanding of the factors that have an important impact on students' outcomes.

### Results and Interpretation

#### Feature Importance:

1. **Total Attempts (Coefficient: -2.197):** More attempts per problem indicate lower chances of success, suggesting students struggle with certain problems.
2. **Hints Used (Coefficient: -2.707):** Higher use of hints correlates with lower success rates, implying dependency on hints is a sign of difficulty.
3. **Time Spent (Coefficient: 0.0):** Time spent per problem does not significantly impact success, suggesting other factors are more crucial.

### Model Performance:
1. **Coefficients:** The logistic regression model's coefficients reveal the influence of each feature on predicting student success, with the direction and magnitude of impact provided for deeper insights.
2. **Accuracy:** The model's accuracy is evaluated using cross-validation, ensuring robustness and generalizability of the predictive power.
    - **Logistic Regression:** The logistic regression model achieved an accuracy of approximately **99.65%**, indicating a high level of predictive performance. This accuracy was validated using cross-validation techniques to ensure the model's generalizability across different datasets.
    - **Random Forest:** Similarly, the random forest model demonstrated a high accuracy of about **99.65%**. The consistency of this accuracy across different modeling techniques underscores the reliability of the predictive insights generated.
  
### Visualization (more in code)
1. **Performance by Grade:** Visualizations show how average scores distributed by grade, providing insights into how different groups perform.
![image](https://github.com/macs30113-s24/final-project-kz/assets/143459510/aef8f80a-147b-47de-821b-db14bdc4235c)
2. **Engagement and Scores Analysis:** Scatter plots highlight the relationship between time spent and scores, revealing patterns in student engagement.
![image](https://github.com/macs30113-s24/final-project-kz/assets/143459510/5e67643b-dfa2-4cad-8361-56d1b2dd60e0)
3. **Comparative Analysis Across Groups** Bar charts indicates performance and engagement between self-coached students and those who are not self-coached.
![image](https://github.com/macs30113-s24/final-project-kz/assets/143459510/a0c7eb68-2023-416d-99b6-658a5640d9da)


### Expected Outcomes

The analysis aims to provide:
1. Insights into factors that most significantly impact student performance.
2. Predictive models that can forecast student success in exercises, enabling personalized learning paths.
3. Recommendations for educational content developers on how to structure exercises to maximize student engagement and success.

### Conclusion

This project not only aims to push the boundaries of applying machine learning to educational data but also seeks to provide actionable insights that can be used by educators and content creators to improve the efficacy of online learning.

### Acknowledgments
This project utilizes the Junyi Academy Online Learning Activity Dataset, a comprehensive dataset released by the Junyi Academy Foundation. Junyi Academy, a non-profit organization based in Taiwan, is committed to providing equitable quality education through technological solutions, supporting a wide range of educational research and practical applications. Their dedication to educational equity and data transparency significantly contributes to the advancement of educational technologies and methodologies.
