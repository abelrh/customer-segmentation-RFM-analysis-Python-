# 📊 Customer Segmentation Analysis | RFM & K-Means Clustering

## 📌 Project Overview

This project focuses on **Customer Segmentation Analysis** using an e-commerce dataset.

The main objective is to segment customers based on their purchasing behavior and identify meaningful customer groups that can help businesses develop **targeted marketing strategies, improve customer retention, and increase customer value**.

The project combines **RFM Analysis** with **K-Means Clustering** to identify distinct customer segments based on their purchasing behavior.

---

## 🎯 Project Objectives

The main objectives of this project are to:

* Clean and prepare the customer transaction data.
* Analyze customer purchasing behavior.
* Calculate key customer metrics.
* Perform **RFM Analysis**.
* Select important behavioral features for clustering.
* Standardize the features before applying clustering.
* Determine the optimal number of clusters using the **Elbow Method**.
* Apply the **K-Means clustering algorithm**.
* Visualize and analyze the resulting customer segments.
* Profile each customer segment.
* Develop targeted marketing recommendations for each segment.

---

## 🗂️ Dataset

The dataset contains e-commerce transaction information that can be used to understand customer purchasing behavior.

### Main Features

| Feature       | Description                           |
| ------------- | ------------------------------------- |
| `InvoiceNo`   | Unique transaction/invoice identifier |
| `StockCode`   | Product identifier                    |
| `Description` | Product description                   |
| `Quantity`    | Number of items purchased             |
| `InvoiceDate` | Date and time of the transaction      |
| `UnitPrice`   | Price per unit                        |
| `CustomerID`  | Unique customer identifier            |
| `Country`     | Customer country                      |

A new feature was also created:

```text
TotalPrice = Quantity × UnitPrice
```

This feature represents the total value of each transaction line.

---

# 🔍 Analysis Performed

## 1. Data Cleaning & Preparation

The dataset was inspected and cleaned before performing the analysis.

The preprocessing steps included:

* Inspecting the dataset structure
* Handling missing values
* Checking for inconsistent data
* Removing invalid records where necessary
* Creating the `TotalPrice` feature
* Preparing the dataset for customer-level analysis

---

## 2. Customer Behavior Analysis

Several customer-level metrics were calculated to understand purchasing behavior.

The analysis focused on:

* Average Purchase Value
* Purchase Frequency
* Monetary Value
* Customer Lifetime Value indicators

These metrics provide a better understanding of customer purchasing patterns.

---

# 📊 3. RFM Analysis

RFM analysis was used to represent customer behavior using three key dimensions:

### 🔹 Recency

How recently a customer made a purchase.

A lower Recency value indicates a more recently active customer.

### 🔹 Frequency

How frequently a customer makes purchases.

Higher Frequency indicates a more engaged customer.

### 🔹 Monetary

How much money a customer has spent.

Higher Monetary values indicate higher-value customers.

### RFM Features

```text
RFM = Recency + Frequency + Monetary
```

These three features were selected as the main behavioral variables for customer segmentation.

---

# ⚙️ 4. Feature Standardization

Before applying K-Means, the RFM features were standardized using **StandardScaler**.

This step is important because Recency, Frequency, and Monetary can have very different scales.

Standardization prevents features with larger numerical values from dominating the clustering algorithm.

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

rfm_scaled = scaler.fit_transform(
    rfm[['Recency', 'Frequency', 'Monetary']]
)
```

---

# 🤖 5. K-Means Clustering

The **K-Means clustering algorithm** was used to divide customers into distinct groups based on their RFM characteristics.

The algorithm assigns customers to clusters based on similarity in their purchasing behavior.

---

## 📐 6. Elbow Method

The **Elbow Method** was used to determine a suitable number of clusters.

Different values of `K` were tested, and the Within-Cluster Sum of Squares (WCSS) was evaluated.

The point where the decrease in WCSS begins to slow down was used as an indication of the appropriate number of clusters.

This helps avoid selecting too few or too many customer segments.

---

# 📈 7. Cluster Visualization

The resulting customer segments were visualized using scatter plots.

Different combinations of RFM features were analyzed, such as:

* Recency vs Frequency
* Frequency vs Monetary
* Recency vs Monetary

These visualizations help understand how customer groups differ from each other.

---

# 👥 8. Customer Segment Profiling

After assigning customers to clusters, each cluster was analyzed using the average RFM values.

The profiles help identify different customer types based on their purchasing behavior.

For example:

| Customer Segment               | Characteristics                          | Potential Strategy        |
| ------------------------------ | ---------------------------------------- | ------------------------- |
| ⭐ High-Value Customers         | High Frequency & Monetary, Low Recency   | Loyalty & VIP programs    |
| 🟢 Loyal Customers             | Frequent purchases and strong engagement | Cross-selling & upselling |
| 🟡 Potential Customers         | Moderate engagement and spending         | Personalized offers       |
| 🔴 At-Risk Customers           | High Recency with previous activity      | Re-engagement campaigns   |
| ⚪ Low-Value/Inactive Customers | Low Frequency & Monetary                 | Low-cost campaigns        |

> The exact characteristics and number of segments depend on the final clustering results.

---

# 📊 9. Customers per Cluster

A bar chart was created to show the number of customers belonging to each cluster.

This helps businesses understand the size of each customer segment and prioritize marketing efforts accordingly.

---

# 💡 Marketing Recommendations

The segmentation results can be translated into targeted marketing actions.

### ⭐ High-Value Customers

**Characteristics:**

* Recent purchases
* High purchase frequency
* High spending

**Recommended Actions:**

* VIP loyalty programs
* Exclusive offers
* Early access to new products
* Personalized recommendations

---

### 🟢 Loyal Customers

**Characteristics:**

* Frequent purchases
* Consistent engagement

**Recommended Actions:**

* Cross-selling
* Upselling
* Loyalty rewards
* Personalized product recommendations

---

### 🟡 Potential Customers

**Characteristics:**

* Moderate purchasing activity
* Potential for higher engagement

**Recommended Actions:**

* Personalized discounts
* Product recommendations
* Promotional campaigns
* Encourage repeat purchases

---

### 🔴 At-Risk Customers

**Characteristics:**

* Previously active customers
* Increasing Recency
* Decreasing engagement

**Recommended Actions:**

* Re-engagement campaigns
* Special discount offers
* Personalized emails
* Limited-time promotions

---

### ⚪ Inactive / Low-Value Customers

**Characteristics:**

* Low purchase frequency
* Low spending
* High Recency

**Recommended Actions:**

* Cost-effective campaigns
* Targeted promotions
* Win-back campaigns
* Avoid excessive marketing spending

---

# 🛠️ Technologies Used

* 🐍 **Python**
* 📊 **Pandas**
* 🤖 **Scikit-learn**
* 📈 **Matplotlib**
* 📉 **Seaborn**
* 📓 **Jupyter Notebook**

### Machine Learning Technique

* **K-Means Clustering**

### Data Analysis Technique

* **RFM Analysis**
* Recency
* Frequency
* Monetary

---

# 📁 Project Structure

```text
Customer-Segmentation/
│
├── 📓 Customer_Segmentation.ipynb
├── 📄 README.md
│
└── 📂 data/
    └── ecommerce_data.csv
```

> Dataset and notebook names may vary depending on the project setup.

---

# ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/your-username/Customer-Segmentation.git
```

### 2. Navigate to the project directory

```bash
cd Customer-Segmentation
```

### 3. Install the required libraries

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 5. Open the notebook

Open:

```text
Customer_Segmentation.ipynb
```

Then run the notebook cells sequentially.

---

# 📌 Key Takeaway

Customer segmentation allows businesses to move away from a **one-size-fits-all marketing strategy** toward more personalized and data-driven customer engagement.

By combining **RFM Analysis** with **K-Means Clustering**, businesses can identify valuable, loyal, potential, and at-risk customers and develop marketing strategies tailored to each segment.

This project demonstrates practical skills in:

* Customer Analytics
* RFM Analysis
* Unsupervised Machine Learning
* K-Means Clustering
* Data Preprocessing
* Feature Scaling
* Data Visualization
* Customer Profiling
* Business Insights
* Marketing Strategy

---

# 👨‍💻 Author

**Abdulrhman**

Aspiring **Data Analyst** passionate about using data analysis and machine learning to generate meaningful insights and support data-driven business decisions.

---

## ⭐ If You Found This Project Useful

Feel free to ⭐ **star this repository** and explore the project!
