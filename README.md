# Customer Segmentation with K-Means Clustering

This project uses **K-Means clustering** to segment customers into groups based on their behaviour, so that marketing and sales teams can target different segments with more relevant campaigns instead of treating all customers the same.

---

## 1. Business Problem

Many organisations have a large customer base but only a limited marketing budget. Sending the same message to everyone is inefficient and often ineffective. The goal of this project is to **discover data-driven customer segments** using unsupervised learning (K-Means), so that we can:

- Understand different customer profiles (e.g. “high spend but low frequency”, “frequent small spenders”).
- Prioritise high-value or high-potential segments.
- Design tailored campaigns for each segment.

This is an **exploratory segmentation** project, not a prediction task: we do not predict a label, we discover structure in the data.

---

## 2. Data

The notebook works with a customer-level dataset that contains features such as:

- **Customer ID**
- **Total spend** over a period
- **Number of transactions** / orders
- **Average order value**
- **Recency** (days since last purchase)
- Possibly **demographic or categorical variables** (e.g. region, channel)

From the raw data we engineer a small set of numerical features suitable for clustering, often inspired by RFM-style analysis (Recency, Frequency, Monetary):

- `recency_days`
- `num_orders`
- `total_spend`
- `avg_order_value`

The exact dataset used is for learning/demo purposes, but the approach can be applied to any transactional customer data.

---

## 3. Approach

**Tools**

- Python, Jupyter Notebook  
- `pandas`, `numpy`  
- `scikit-learn` (KMeans, scaling)  
- `matplotlib` / `seaborn` for visualisation

**Steps**

1. **Data Preparation**
   - Load customer-level data.
   - Handle missing values and outliers where necessary.
   - Create behavioural features (recency, frequency, monetary metrics).

2. **Feature Scaling**
   - Standardise or normalise numerical features (e.g. `StandardScaler`) so that all variables contribute fairly to the distance calculations used by K-Means.

3. **Choosing Number of Clusters (k)**
   - Use **Elbow method** and/or **Silhouette scores** to explore different values of `k`.
   - Pick a reasonable `k` that balances model simplicity with separation between clusters.

4. **K-Means Clustering**
   - Fit K-Means with the selected `k`.
   - Assign each customer a **cluster label**.

5. **Cluster Profiling**
   - Compute average feature values per cluster.
   - Interpret each cluster as a **segment** (e.g. “high-value loyal customers”, “price-sensitive occasional buyers”, etc.).
   - Visualise clusters using pairplots, scatter plots (e.g. total spend vs frequency), or 2D projections.

---

## 4. Results – Example Segments

Exact cluster descriptions depend on the dataset and chosen features, but typical segments might include:

- **Segment 1 – High-value loyal customers**  
  High total spend, high frequency, relatively low recency (recent purchases).

- **Segment 2 – Regular mid-value customers**  
  Moderate spend and frequency, stable purchasing pattern.

- **Segment 3 – Infrequent but high-order-value customers**  
  Few orders but each order is large; candidates for upsell or nurture campaigns.

- **Segment 4 – Low-value / dormant customers**  
  Low spend and frequency, high recency; potential targets for reactivation campaigns.

The notebook includes visualisations (e.g. scatter plots coloured by cluster and summary tables by cluster) to support these interpretations.

---

## 5. How to Run

1. Clone the repository or download it as a ZIP.
2. Ensure you have Python 3.9+ and install the required libraries:
   - `pandas`
   - `numpy`
   - `scikit-learn`
   - `matplotlib`
   - `seaborn` (optional)
3. Open the main notebook, for example:

   - `01_customer_segmentation_kmeans.ipynb`

4. Run all cells from top to bottom.

If you do not have the original dataset, you can replace it with your own customer data that includes similar features (recency, frequency, monetary values) and follow the same steps.

---

## 6. Possible Extensions

- Add **RFM scoring** and compare score-based segments with K-Means segments.
- Use **alternative clustering methods** (e.g. hierarchical clustering, DBSCAN) and compare results.
- Enrich the data with **channel, product category or demographic features** and examine how segments differ on these dimensions.
- Integrate the segments into a **dashboard** (e.g. Power BI / Streamlit app) so that non-technical users can filter and explore segment profiles easily.
