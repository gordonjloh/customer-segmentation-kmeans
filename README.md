# App User Segmentation with K-Means

This project uses **K-Means clustering** to segment app users based on their age, number of sessions per week and average session duration. The goal is to move from a one-size-fits-all engagement strategy to **data-driven user segments** that marketing and product teams can target differently.

## Data

Each row represents a user, with:

- `age`
- `sessions_per_week` – how often they use the app
- `avg_session_duration` – average session length in minutes

## Approach

1. Load and inspect the user-level data.
2. Select the behavioural features (`age`, `sessions_per_week`, `avg_session_duration`).
3. Standardise features using `StandardScaler`.
4. Use the elbow method to select an appropriate number of clusters (k).
5. Fit **K-Means** on the scaled data and assign each user a cluster label.
6. Profile clusters by averaging the features within each cluster.
7. Visualise clusters in a scatter plot of sessions per week vs average session duration.

## Results (Example Segments)

From this dataset, the model finds segments such as:

- **Cluster 0 – Light, quick users:** fewer sessions and short durations.
- **Cluster 1 – Occasional but deep users:** 1–2 sessions per week but longer sessions.
- **Cluster 2 – Heavy, highly engaged users:** frequent sessions and long durations.

These segments can guide **different engagement and marketing strategies** for light, occasional and heavy users.

## How to Run

- Python 3.9+
- Libraries: `pandas`, `numpy`, `scikit-learn`, `matplotlib`

Open the notebook `01_customer_segmentation_kmeans.ipynb` and run all cells from top to bottom.
