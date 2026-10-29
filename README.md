Lab 2: Country Schools Dataset

This project analyses the Country Schools dataset, which has one row for each of 47 counties. For each county it records the total number of schools, how many schools have been installed with devices, how many are still pending, the percentage installed, and the number of learner and teacher devices installed. The notebook covers data preprocessing, anomaly detection and cluster analysis. The Kaggle notebook is here: <paste your link>.

The raw file needed cleaning before it could be used. It had two blank rows and a TOTAL row that summarises all the counties, so I removed those. I also converted the percentage column from text to a number, tidied the county names, dropped the row id, and checked that the numbers were consistent. Finally, I standardised the features so that large numbers, such as device counts, would not dominate small ones, such as percentages.

For anomaly detection I used four methods: the Z-score, the IQR rule, Isolation Forest and Local Outlier Factor. Kitui was flagged by all four, Makueni by three and Kakamega by two. Their numbers are internally consistent, so they are genuine extremes (very large counties, or an unusual mix of values) and not data errors.

For cluster analysis I used K-Means, choosing four clusters with the elbow method and the silhouette score, and I cross-checked the result with hierarchical clustering and a PCA plot. The counties fall into four groups: small and nearly done, medium-large with the biggest backlog, small and far behind, and large and well covered. The most notable group is six counties (Turkana, Garissa, Mandera, Wajir, Marsabit and Samburu) where only about 13 percent of schools are installed.

The main limitations are that there are only 47 rows, so the results depend on choices like the number of clusters, and that the data is a single snapshot that cannot explain why some counties are behind.

To run it, upload Country_Schools.csv as a Kaggle dataset, add it to the notebook and click Run All. Locally, keep the notebook and CSV in the same folder.
