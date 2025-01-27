# Lookalike Model

This repository contains the implementation of a **Lookalike Model** that recommends similar customers based on their profile and transaction history. The model utilizes customer and product information to compute similarity scores and outputs the top 3 lookalikes for the first 20 customers.

---

## Files in this Repository

1. **`Lookalike_Model.py`**: Python script that contains the complete implementation of the Lookalike Model.
2. **`Lookalike.csv`**: Output file containing the top 3 similar customers and their similarity scores for the first 20 customers (CustomerID: C0001 - C0020).
3. **`Customers.csv`**: Dataset containing customer information.
4. **`Products.csv`**: Dataset containing product information.
5. **`Transactions.csv`**: Dataset containing transaction details.

---

## Steps in the Lookalike Model

### 1. **Data Loading**
   - The script reads three input datasets: `Customers.csv`, `Products.csv`, and `Transactions.csv`.

### 2. **Data Preprocessing**
   - **One-Hot Encoding**: Encodes the `Region` column from `Customers.csv` using OneHotEncoder.
   - **Feature Transformation**: Converts the `SignupDate` column into the number of days since signup.

### 3. **Feature Normalization**
   - Features are scaled using `StandardScaler` to ensure uniformity and improve similarity computation.

### 4. **Similarity Computation**
   - Uses **cosine similarity** to measure the closeness of customers based on their normalized features.

### 5. **Finding Lookalikes**
   - For each customer, the script identifies the top 3 most similar customers based on the similarity scores. Self-similarity is excluded.

### 6. **Output Generation**
   - The results are saved in a CSV file named `Lookalike.csv`. It contains the mapping of each customer's ID to their top 3 similar customers and their respective similarity scores.

---

