# Business Analytics & AI Project

## Question
How do total mental health scores compare across different education levels?

## Dataset
Dataset: AI & Social Media Impact: Student Health & Grades

Kaggle: https://www.kaggle.com/datasets/srisyra02/ai-and-social-media-impact-student-health-and-grades

Each row represents one student and includes information such as age,
education level, daily social media usage, daily AI tool usage, sleep,
physical activity, and mental and physical health scores.

## Python + AI
I loaded and inspected a dataset containing 16,000 student records and checked
for duplicate rows and missing values. The dataset contained no duplicates or
missing values, so all 16,000 records were retained. The chart shows total mental health scores across different education levels.

## SQL

**Q1. How many students have a mental health score above 75?**
```sql
SELECT COUNT(*) AS students_above_75
FROM data
WHERE mental_health_score > 75
```
**Finding:** 7,104 students had a mental health score above 75.

**Q2. Which education level has the highest total mental health score?**
```sql
SELECT education_level,
    SUM(mental_health_score) AS total_mental_health_score
FROM data
GROUP BY education_level
ORDER BY total_mental_health_score DESC
```
**Finding:** High School students had the highest total mental health score at 440,071.90.

**Q3. What are the top 5 ages by average mental health score among University students?**
```sql
SELECT age,
    AVG(mental_health_score) AS avg_mental_health_score
FROM data
WHERE education_level = 'University'
GROUP BY age
ORDER BY avg_mental_health_score DESC
LIMIT 5
```
**Finding:** Among University students, age 22 had the highest average mental health score at 72.88.
