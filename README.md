# 🛍️ Mall Customer Segmentation: K-Means Clustering

This project utilizes **Unsupervised Machine Learning** to group retail customers based on their annual income and spending habits. By identifying distinct customer segments, businesses can tailor their marketing strategies to specific consumer behaviors.

## 📊 Dataset Overview
The `mallcustomers.csv` dataset includes information on 200 customers:
* **Features:** Gender, Age, Annual Income, and Spending Score (1-100).
* **Objective:** Discover natural groupings within the customer base to define personas.

## 🛠 Technical Workflow

### 1. Data Preprocessing
* **String Cleaning:** Removed currency symbols ("USD") and commas from the Income column.
* **Type Conversion:** Converted income data to numeric format for mathematical analysis.
* **Feature Scaling:** Applied `StandardScaler` to normalize **Income** and **Spending Score**, ensuring both features contribute equally to distance calculations in the clustering algorithm.

### 2. Finding the Optimal Clusters
I utilized the **Elbow Method** to determine the ideal number of clusters ($k$).
* Calculated the Within-Cluster Sum of Squares (WCSS) for $k$ values ranging from 1 to 10.
* Identified $k=5$ as the "elbow" point, where adding more clusters yielded diminishing returns in variance reduction.

### 3. K-Means Clustering & Evaluation
With $k=5$, the model successfully identified five distinct customer personas:
* **Cluster 0:** Average Income, Average Spending
* **Cluster 1:** High Income, High Spending (Target for Luxury)
* **Cluster 2:** Low Income, High Spending (High Engagement)
* **Cluster 3:** High Income, Low Spending (Target for Value/Savings)
* **Cluster 4:** Low Income, Low Spending

## 📈 Key Insights
By performing a post-cluster analysis on demographics:
* **Age Distribution:** Analyzed the mean age for each cluster to identify generational spending habits.
* **Gender Analysis:** Converted categorical gender data into dummy variables to see how gender proportions shifted across different spending segments.

---

### 🚀 How to Run
1. Ensure `mallcustomers.csv` is in the root directory.
2. Install dependencies: `pip install pandas numpy scikit-learn matplotlib`
3. Execute the script to generate the Elbow Curve and the final Cluster Scatter Plot.
