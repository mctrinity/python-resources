# 📌 Software Engineer Job Test Preparation

## **1️⃣ Python Programming**
### 📝 Sample Questions

#### **Q1: Reverse a String Without Built-in Functions**
```python
# Implement function to reverse a string
def reverse_string(s):
    pass  # Implement logic

print(reverse_string("hello"))  # Expected Output: "olleh"
```

#### **Q2: Find the Most Frequent Element in a List**
```python
# Function to find the most frequent element in a list
def most_frequent(lst):
    pass  # Implement logic

print(most_frequent([1, 3, 3, 2, 1, 3, 1]))  # Expected Output: 3
```

---

## **2️⃣ API Development (REST APIs)**
### 📝 Sample Questions

#### **Q3: Build a Simple Flask API Endpoint**
```python
from flask import Flask

app = Flask(__name__)

@app.route('/hello', methods=['GET'])
def hello():
    return {"message": "Hello, World!"}

if __name__ == "__main__":
    app.run(debug=True)
```

#### **Q4: Create an API That Accepts JSON Payload and Returns Sum of Two Numbers**
```python
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/add', methods=['POST'])
def add_numbers():
    data = request.json
    result = data['num1'] + data['num2']
    return jsonify({"sum": result})

if __name__ == "__main__":
    app.run(debug=True)
```

---

## **3️⃣ SQL Queries & Database (Snowflake, SQL)**
### 📝 Sample Questions

#### **Q5: Retrieve Top 5 Customers by Total Purchase Amount**
```sql
SELECT customer_id, SUM(amount) AS total_spent
FROM orders
GROUP BY customer_id
ORDER BY total_spent DESC
LIMIT 5;
```

#### **Q6: Find Duplicate Records in a Table**
```sql
SELECT user_id, COUNT(*)
FROM users
GROUP BY user_id
HAVING COUNT(*) > 1;
```

---

## **4️⃣ Azure & Databricks**
### 📝 Sample Questions

#### **Q7: How to Deploy an Azure Function Using Python?**
- What are the steps to deploy an Azure Function using Python?
- How do you trigger an Azure Function using HTTP or Event Hub?

#### **Q8: Write a PySpark Script to Process Large Data in Databricks**
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("Data Processing").getOrCreate()
data = spark.read.csv("data.csv", header=True, inferSchema=True)
data.show()
```

---

## **5️⃣ Git & VS Code**
### 📝 Sample Questions

#### **Q9: How Do You Create a New Git Branch?**
```bash
git checkout -b new-feature
```

#### **Q10: How Do You Push a Local Branch to GitHub?**
```bash
git push origin new-feature
```

---

### 🚀 **Final Tips**
✅ Practice **Python, SQL, API development, Azure, and Git**.
✅ Use **efficient and clean code**.
✅ Optimize queries and functions.
✅ Be prepared for **real-world coding scenarios**.

💡 **Best of luck!** 🎯
