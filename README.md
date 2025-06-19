[task1_cleaned.xlsx](https://github.com/user-attachments/files/20625705/task1_cleaned.xlsx)
[task1.xlsx](https://github.com/user-attachments/files/20625699/task1.xlsx)


https://github.com/user-attachments/assets/369a6743-8a3f-4736-984c-5cda75c84a4d

# 🚀 FUTURE_DS_01: Social Media Trend Analysis  

## 🏆 Internship Program: Future Interns - Data Science & Analytics  
This project focuses on analyzing **trending topics, sentiment shifts, and user engagement** across **Facebook, Twitter, and Instagram** using **Python and Power BI**.

---

## 📌 **Key Insights**
✔ **Most trending topics:** Travel, fitness, AI, technology  
✔ **Positive sentiment dominates social media discussions**  
✔ **Event-based hashtags** gain traction closer to their dates  
✔ **Brands should focus on popular hashtags** to maximize engagement  

## 📊 **Power BI Dashboard Insights**
✔ **Sentiment Analysis Pie Chart** → Breakdown of **Positive, Neutral, Negative** posts  
✔ **Trending Hashtags Bar Chart** → Most-used hashtags  
✔ **User Engagement Line Chart** → Likes & retweets trends  

---

## **🔹 Data Processing & Sentiment Analysis**  
### **Step 1: Data Cleaning**
```python
import pandas as pd
import re

# Load dataset
file_path = r"C:\Users\kdala\Documents\task one project work.py"
df = pd.read_excel(file_path)

# Clean missing values & format timestamps
df.dropna(inplace=True)
df['Timestamp'] = pd.to_datetime(df['Timestamp'])

# Normalize text data
df['Text'] = df['Text'].apply(lambda x: re.sub(r'[^a-zA-Z\s]', '', str(x).lower()))



Step 2: Sentiment Analysis Using TextBlob
from textblob import TextBlob

df['Sentiment_Score'] = df['Text'].apply(lambda x: TextBlob(x).sentiment.polarity)
df['Sentiment_Category'] = df['Sentiment_Score'].apply(lambda x: 'Positive' if x > 0 else ('Negative' if x < 0 else 'Neutral'))![1]

✅ Key Findings: ✔ Positive sentiment dominates travel, fitness, and tech posts.
                  ✔ Negative sentiment mostly links to debates, news, and complaints.

Step 3: Extracting Trending Hashtags

from collections import Counter

hashtags = Counter(df['Hashtags'].str.split().sum())
print(hashtags.most_common(10)) # Display top trending hashtags



 











