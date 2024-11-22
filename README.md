Customer Segmentation and Analysis

Overview

This project focuses on segmenting customers based on their purchasing behavior using clustering techniques like K-Means and DBSCAN. The goal is to identify distinct customer groups to enable targeted marketing, personalized recommendations, and improved customer retention strategies.

Project Features

Preprocessing of customer data for segmentation.
Implementation of K-Means and DBSCAN clustering algorithms.
Evaluation of cluster quality using Elbow Method and Silhouette Score.
Dimensionality reduction with PCA for visualization.
Detailed cluster analysis and actionable insights for business applications.

Technologies Used

Python: Primary programming language.

Libraries:

Pandas and NumPy: For data preprocessing and manipulation.
Scikit-learn: For clustering and evaluation.
Matplotlib and Seaborn: For visualization.
PCA: For dimensionality reduction.

Dataset

The dataset used in this project contains customer transaction details such as:

Family Size: The number of family members in the customer's household.
Spending Score (1–100): A score assigned to the customer based on their spending patterns and habits (higher scores indicate higher spending tendencies).
Age: The age of the customer in years.
Note: Replace data.csv with your actual dataset file. Ensure sensitive data is anonymized before publishing.

Setup and Installation
1.Clone the repository:
git clone https://github.com/yourusername/customer-segmentation.git
cd customer-segmentation

2.Install the required libraries:
pip install -r requirements.txt

3.Add your dataset file (e.g., data.csv) to the project directory.
Usage:
1.Run the main Python script to preprocess data, perform clustering, and visualize the results:
python customer_segmentation.py

2.The script will:
Apply clustering algorithms to segment customers.
Save the segmented data as segmented_customers.csv in the project directory.
Display visualizations of the clusters.

Output
The final dataset includes:

An additional column, Cluster, representing the assigned customer segment.
Example output:

CustomerID	Recency	Frequency	Monetary	Cluster
1	15	10	1000	1
2	30	5	500	0
3	7	20	1500	2

Visualizations:

Scatter plots of clusters in 2D space (using PCA).
Elbow Curve for optimal K in K-Means.

Project Structure

customer-segmentation/
├── data.csv                  # Input dataset (replace with your dataset)
├── customer_segmentation.py  # Main script for clustering and analysis
├── requirements.txt          # Python dependencies
├── README.md                 # Project documentation
└── outputs/
    └── segmented_customers.csv  # Segmented data with cluster labels

Key Results

Clusters Identified: Segmentation of customers into distinct groups.
Cluster Analysis: Detailed insights into customer segments.
Visualizations: PCA-based visualization of customer clusters.

Future Improvements

Incorporate additional features (e.g., customer demographics, product categories).
Experiment with other clustering techniques like Hierarchical Clustering.
Automate hyperparameter tuning for optimal clustering.

Contributing

Contributions are welcome! Feel free to submit issues or pull requests.

License

This project is licensed under the MIT License. See LICENSE for more details.

Contact

For questions or feedback, contact:

Your Name: mohamedmuntasirs.ug22.ad@francisxavier.ac.in

GitHub Profile: https://github.com/mohamedmunthasirs23
