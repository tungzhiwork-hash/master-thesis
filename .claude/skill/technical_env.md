# Môi Trường Kỹ Thuật — Python

## Phiên bản và thư viện cốt lõi

```python
# Môi trường Python khuyến nghị
python >= 3.10

# Core ML
pandas >= 2.0
numpy >= 1.24
scikit-learn >= 1.3
xgboost >= 2.0
lightgbm >= 4.0
catboost >= 1.2
shap >= 0.44
imbalanced-learn >= 0.11  # SMOTE

# Visualization
matplotlib >= 3.7
seaborn >= 0.12

# Hyperparameter tuning
optuna >= 3.0

# Statistical analysis
scipy >= 1.11
statsmodels >= 0.14
pingouin >= 0.5           # Test thống kê nâng cao (nếu cần)
```

## Cài đặt môi trường

```bash
# Tạo virtual environment
python -m venv thesis_env
source thesis_env/bin/activate  # Linux/Mac
thesis_env\Scripts\activate     # Windows

# Cài đặt tất cả dependencies
pip install pandas numpy scikit-learn xgboost lightgbm catboost shap imbalanced-learn matplotlib seaborn optuna scipy statsmodels pingouin
```

## Môi trường Jupyter

```bash
pip install jupyter jupyterlab ipykernel
python -m ipykernel install --user --name thesis_env --display-name "Thesis ML"
```

## Quy ước tổ chức notebook

```
notebooks/
├── 01_eda.ipynb              # EDA
├── 02_preprocessing.ipynb    # Tiền xử lý
├── 03_modeling.ipynb         # Huấn luyện mô hình
├── 04_evaluation.ipynb       # Đánh giá
├── 05_shap_analysis.ipynb    # Phân tích SHAP
└── 06_business_insights.ipynb # Diễn giải nghiệp vụ
```
