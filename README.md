# DSA2040A_DataMining_Group4

# Cybersecurity Intrusion Data Mining Project

## Overview

This project analyzes cybersecurity intrusion data using both supervised and unsupervised machine learning techniques, as well as association rule mining. The workflow covers data extraction, transformation, exploratory data analysis, modeling, clustering, and association rule mining to uncover patterns and insights related to network attacks.

## Project Structure

```
1_extract_transform.ipynb         # Data extraction, cleaning, and transformation
2_exploratory_data_analysis.ipynb # Exploratory data analysis (EDA)
3_data_mining.ipynb               # Data mining: modeling, clustering, association rules
cybersecurity_intrusion_data.csv  # Raw data file
README.md                         # Project documentation
data/
    processed/
        eda_processed_cybersecurity_data.csv
    raw/
        cybersecurity_intrusion_data.csv
    transformed/
        transformed_cybersecurity_intrusion_data.csv
```

## Data Description

The dataset contains network session records with the following columns:

- `usession_id`: Unique session identifier
- `network_packet_size`: Size of network packets (bytes)
- `protocol_type`: Protocol used (TCP, UDP, ICMP)
- `login_attempts`: Number of login attempts in the session
- `session_duration`: Duration of the session (seconds)
- `encryption_used`: Encryption protocol used (e.g., AES, DES, None)
- `ip_reputation_score`: Reputation score of the IP address
- `failed_logins`: Number of failed login attempts
- `browser_type`: Browser used
- `unusual_time_access`: Whether access occurred at an unusual time (0/1)
- `attack_detected`: Whether an attack was detected (0/1)

## Workflow

### 1. Data Extraction & Transformation

- Performed in [1_extract_transform.ipynb](1_extract_transform.ipynb).
- Loads raw data, checks for missing values and duplicates, and applies necessary cleaning:
  - Fills missing values in `encryption_used` with `"None"`.
  - Ensures consistent casing for categorical columns.
  - Removes duplicates (if any).
  - Saves the cleaned data to `data/transformed/transformed_cybersecurity_intrusion_data.csv`.

### 2. Exploratory Data Analysis (EDA)

- Conducted in [2_exploratory_data_analysis.ipynb](2_exploratory_data_analysis.ipynb).
- Visualizes distributions, checks for outliers, and summarizes key statistics.

### 3. Data Mining

All data mining steps are in [3_data_mining.ipynb](3_data_mining.ipynb):

#### a. Data Preparation

- Loads the transformed dataset.
- Drops `usession_id` and handles missing values.
- Encodes categorical variables using `LabelEncoder`.
- Scales numerical features with `StandardScaler`.
- Splits data into features (`X`) and target (`y`).

#### b. Supervised Learning

- **Models Used:** Logistic Regression, Decision Tree, Random Forest.
- **Evaluation:** Accuracy, precision, recall, F1-score, and confusion matrices.
- **Best Model:** Random Forest (highest accuracy and F1-score for attack detection).

#### c. Unsupervised Learning

- **KMeans Clustering:**
  - Uses the elbow method to determine optimal clusters (k=4).
  - Visualizes clusters using PCA.
  - Analyzes cluster characteristics and their relation to attacks.
- **DBSCAN:**
  - Detects clusters and noise (outliers).
  - Compares DBSCAN clusters with attack labels.

#### d. Association Rule Mining

- Prepares data by binarizing and one-hot encoding relevant features.
- Applies the Apriori algorithm to find frequent itemsets.
- Generates association rules (using `mlxtend`).
- **Key Insight:** Sessions with attacks have a high likelihood (87% confidence) of at least one failed login.

## How to Run

1. **Install dependencies:**
   - Python 3.x
   - pandas, numpy, scikit-learn, matplotlib, seaborn, mlxtend

   ```sh
   pip install pandas numpy scikit-learn matplotlib seaborn mlxtend
   ```

2. **Run notebooks in order:**
   - Start with [1_extract_transform.ipynb](1_extract_transform.ipynb) to clean and transform the data.
   - Proceed to [2_exploratory_data_analysis.ipynb](2_exploratory_data_analysis.ipynb) for EDA.
   - Finish with [3_data_mining.ipynb](3_data_mining.ipynb) for modeling, clustering, and association rule mining.

## Results & Insights

- **Random Forest** is the best model for attack detection (accuracy: 0.89, perfect precision for attacks).
- **Failed logins** are highly predictive of attacks (87% confidence in association rules).
- **Cluster analysis** reveals groups with higher login attempts are more likely to be associated with attacks.

## Contributors

- Hetal_207
- Chad_884
- Marilyn

---

For more details, see the individual notebooks and