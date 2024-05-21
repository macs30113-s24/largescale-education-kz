# 30113 Final Project: Online Education Participation Analysis Using Large-Scale Data

**Project Overview**

With the rapid transition to digital platforms in education, understanding student engagement and performance in online learning environments has become an esssential area of focus. This project utilizes a large-scale dataset provided by Junyi Academy, consisting of over 16 million exercise logs from more than 72,000 students, spanning from August 2018 to July 2019. The goal is to use this rich dataset to predict student performance and engagement patterns, facilitating the development of more effective and personalized online learning experiences.

**Research Problem**

The central research problem of this project is to analyze and predict student success and engagement in online exercises based on their interaction data. This involves understanding various factors that influence student performance, including the complexity of exercises, student demographics, previous performance history, and engagement metrics such as time spent and attempts made per problem.

**Importance of Scalable Computing**

Given the extensive volume and granularity of the data involved, traditional data processing methods are insufficient and inefficient. In order to manage, process, and analyze the vast amount of data in an effective way and obtain actionable insights within a reasonable timeframe, scalable computing methods are necessary. This project uses a variety of scalable computing strategies, such as parallel data processing and machine learning algorithms optimized for large datasets, to ensure that the analysis is both reliable and efficient.

**Scalable Computing Methods Used**

1. **Data Processing at Scale:** Utilizing Spark to handle large-scale data transformation and preprocessing. Spark's ability to perform in-memory computations significantly speeds up data processing tasks such as filtering, aggregation, and joining multiple data sources.
2. **Machine Learning at Scale:** Implementing machine learning models using Spark MLlib to predict student performance. MLlib provides a suite of scalable machine learning algorithms which are designed to efficiently run on big data.
3. **Distributed Data Storage:** Storing and managing data using Amazon S3 and integrating it seamlessly with Spark for distributed processing. This step ensures that data accessibility and management are optimized for high performance and scalability.
4. **Visualization and Reporting:** Developing interactive dashboards using Plotly, hosted on AWS to ensure scalability and real-time data interaction.

**Dataset Description**

The dataset comprises three main files:
1. Info_Content.csv: Metadata about the exercises, including their difficulty level and subject.
2. Info_UserData.csv: Demographic and educational background of the students.
3. Log_Problem.csv: Records of student problem-solving attempts, including timestamps, correctness, and hints used.

**Predictive Modeling**

The project applies several predictive models to estimate future student performance on new exercises. Techniques such as logistic regression, random forests, and gradient boosting are employed to model the likelihood of a student achieving a correct answer on the first attempt based on their prior activity.

**Expected Outcomes**

The analysis aims to provide:
1. Insights into factors that most significantly impact student performance.
2. Predictive models that can forecast student success in exercises, enabling personalized learning paths.
3. Recommendations for educational content developers on how to structure exercises to maximize student engagement and success.

**Conclusion**
This project not only aims to push the boundaries of applying machine learning to educational data but also seeks to provide actionable insights that can be used by educators and content creators to improve the efficacy of online learning.

**Acknowledgments**
This project utilizes the Junyi Academy Online Learning Activity Dataset, a comprehensive dataset released by the Junyi Academy Foundation. Junyi Academy, a non-profit organization based in Taiwan, is committed to providing equitable quality education through technological solutions, supporting a wide range of educational research and practical applications. Their dedication to educational equity and data transparency significantly contributes to the advancement of educational technologies and methodologies.
