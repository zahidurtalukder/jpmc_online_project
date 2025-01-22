# Loan Default Prediction Project

## **Project Structure**

The repository is organized into the following files and folders:

- **`01_eda.ipynb`**: Contains the exploratory data analysis (EDA) steps, including data cleaning, visualization, and initial insights.
- **`02_model.ipynb`**: Implements the machine learning pipeline, including preprocessing, model training, validation, and evaluation.
- **`training_loan_data.csv`**: Main training data for EDA and model training (not included in the repo due to policy).
- **`cleaned_train_data.csv`**: The preprocessed training data saved after EDA (not included in the repo due to policy).
- **`testing_loan_data.csv`**: The test dataset (bad_flag is intentionally left blank and not included in the repo due to policy).
- **`dict_data.json`**: Metadata information about the dataset.
- **`requirements.txt`**: Containing requirements for running this project.
- **`.gitignore`**: Specifies files and folders to ignore in the Git repository.
- **`README.md`**: Explains the project structure, running instructions, and assumptions.

## **How to Run the Code**

### 1. **Clone the Repository**
```bash
git clone https://github.com/zahidurtalukder/jpmc_online_project.git
cd jpmc_online_project
```

### 2. **Set Up the Environment**

Ensure you have Python 3.8 or above installed. Then, create a virtual environment and install dependencies:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. **Run EDA**

1. Open the `01_eda.ipynb` notebook.
2. Execute the cells to perform data cleaning, preprocessing, and visualization.
3. Save the cleaned data (`cleaned_train_data.csv`) after completing the EDA.

### 4. **Run Model Training**

1. Open the `02_model.ipynb` notebook.
2. Load the cleaned training data.
3. Execute the cells to train and validate the model.
4. Evaluate the model's performance and adjust hyperparameters if needed.

### 5. **Run Test Inference**

1. Ensure the `testing_loan_data.csv` file is present in the working directory.
2. Follow the test inference section in `02_model.ipynb` to preprocess the test data and generate predictions.
3. Save the predictions as a CSV file (e.g., `test_predictions.csv`).

### 6. **Push Changes to GitHub**

1. Commit changes incrementally as per Git guidelines.
2. Push changes to your GitHub repository:
   ```bash
   git add .
   git commit -m "Your commit message"
   git push origin main
   ```

## **Environment Dependencies**

Install the following Python packages:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- imbalanced-learn
- torch (PyTorch)
- tqdm

You can install all dependencies using:
```bash
pip install -r requirements.txt
```

## **Assumptions Made**

1. **Handling Missing Data**:
   - `mths_since_last_major_derog`: Missing values are imputed with 999.
   - `mths_since_recent_inq`: Missing values are imputed with 36.
   - Numerical columns are filled with their median values.

2. **Feature Engineering**:
   - Categorical columns (`home_ownership`, `purpose`) are one-hot encoded.
   - The target column (`bad_flag`) is treated as binary (0/1).

3. **Scaling**:
   - Numerical features are scaled using `StandardScaler` for model training.

4. **Modeling**:
   - A stratified split is used to preserve class proportions in train-test splits.
   - Oversampling is applied to handle class imbalance, ensuring the positive class makes up 20% of the training data.

5. **Evaluation**:
   - Metrics such as Precision, Recall, F1 Score, and AUC are used for evaluation.
   - The best threshold for classification is determined based on the highest F1 Score.

6. **Test Dataset**:
   - The test dataset is preprocessed to align with the training features.
   - No labels (`bad_flag`) are present in the test set.

## **Contact**
For any queries, please contact Zahidur Talukder at [zahidurtalukder@mavs.uta.edu](mailto:zahidurtalukder@mavs.uta.edu).

