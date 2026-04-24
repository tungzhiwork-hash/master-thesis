# ML Pipeline Chuẩn cho Credit Scoring

## Pipeline 9 bước (bắt buộc đủ thứ tự)

```python
# 1. Data Loading & Exploratory Data Analysis (EDA)
# 2. Preprocessing: missing values, encoding, scaling
# 3. Class imbalance handling (SMOTE hoặc class_weight)
# 4. Feature selection / engineering
# 5. Model training: Logistic Regression (baseline) + Ensemble models
# 6. Hyperparameter tuning (GridSearchCV / Optuna)
# 7. Evaluation: AUC-ROC, F1, Precision, Recall, KS Statistic, Gini
# 8. Interpretability: SHAP values (global + local)
# 9. Business translation: cutoff optimization theo chi phí vỡ nợ
```

## Bộ mô hình so sánh

```python
models = {
    "Logistic Regression": LogisticRegression(),          # Baseline truyền thống
    "Random Forest": RandomForestClassifier(),             # Ensemble cơ bản
    "XGBoost": XGBClassifier(),                           # State-of-the-art (Chang et al., 2022)
    "LightGBM": LGBMClassifier(),                         # Tốt nhất cho VN (Tran et al., 2025)
    "CatBoost": CatBoostClassifier(verbose=0),            # Xử lý categorical tốt
}
```

## Chỉ số đánh giá bắt buộc

| Chỉ số | Lý do bắt buộc |
|--------|---------------|
| AUC-ROC | Tiêu chuẩn ngành credit scoring |
| KS Statistic | Phổ biến trong ngân hàng Việt Nam |
| Gini Coefficient | Biến thể của AUC, yêu cầu của Basel |
| F1-Score | Cân bằng precision/recall |
| Precision / Recall | Phân tích Type I/II error |
| Confusion Matrix | Trực quan hóa sai số phân loại |

## SHAP — Bắt buộc với mọi ensemble model

SHAP explanation là yêu cầu bắt buộc để đáp ứng:
- Tính minh bạch theo Basel III
- Thông tư NHNN về kiểm soát nội bộ và quản trị rủi ro

```python
import shap

# Global explanation
explainer = shap.TreeExplainer(model)
shap_values = explainer.shap_values(X_test)
shap.summary_plot(shap_values, X_test)

# Local explanation (một khách hàng cụ thể)
shap.force_plot(explainer.expected_value, shap_values[0], X_test.iloc[0])
```

## Nguồn dữ liệu được phép sử dụng
- Kaggle public datasets (LendingClub, Give Me Some Credit, Home Credit)
- Báo cáo thường niên NHNN
- Dữ liệu phỏng vấn chuyên gia ngân hàng (sơ cấp)
- **Không được** tự tạo số liệu — ghi `[DỮ LIỆU CẦN THU THẬP]` nếu thiếu
