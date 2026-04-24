# Thesis Glossary — Hướng Dẫn Sử Dụng

Kho từ điển thuật ngữ học thuật dùng cho luận văn "Ứng dụng phân tích dữ liệu và máy học vào hoàn thiện quy trình quản trị rủi ro tín dụng tại ngân hàng thương mại Việt Nam".

## Cấu trúc thư mục

```
thesis-glossary/
├── README.md                      ← File này
├── index.md                       ← Master index toàn bộ từ khóa (A–Z)
├── finance-banking/               ← Tài chính – Ngân hàng
├── ai-machine-learning/           ← AI – Machine Learning
├── statistics-econometrics/       ← Thống kê – Kinh tế lượng
├── tech-management/               ← Quản trị Công nghệ
└── regulatory-legal/              ← Pháp lý – Quy định
```

## Cách thêm thuật ngữ mới

**Cách 1 — Dùng Glossary Agent (khuyến nghị):**
```
[GLOSSARY] Thêm term: Non-Performing Loan
[GLOSSARY] Giải thích XGBoost là gì?
[GLOSSARY] Thêm loạt term: SHAP, LIME, AUC-ROC, F1-score
```

**Cách 2 — Tạo file thủ công:**
1. Xác định thư mục con phù hợp (xem bảng phân loại bên dưới)
2. Đặt tên file: lowercase, dấu gạch ngang, không dấu tiếng Việt
   - Ví dụ: `non-performing-loan.md`, `xgboost.md`, `basel-iii.md`
3. Copy schema từ `../.claude/skill/glossary_management.md`
4. Điền đầy đủ YAML frontmatter và 6 section nội dung
5. Thêm 1 dòng vào `index.md` theo đúng chữ cái

## Bảng phân loại thư mục

| Thư mục | Loại thuật ngữ |
|---------|----------------|
| `finance-banking/` | Tài chính, ngân hàng, tín dụng: NPL, LTV, credit score, collateral, provision |
| `ai-machine-learning/` | ML/DL/AI: XGBoost, SHAP, AUC-ROC, SMOTE, overfitting, feature importance |
| `statistics-econometrics/` | Thống kê & kinh tế lượng: logistic regression, panel data, Cronbach Alpha, EFA |
| `tech-management/` | Quản trị & chiến lược: digital transformation, technology adoption, framework |
| `regulatory-legal/` | Pháp lý & chuẩn mực: Basel III, Thông tư 11/2021/TT-NHNN |

> Nếu một term thuộc nhiều nhóm: chọn thư mục gốc của khái niệm, dùng `related_terms` để liên kết.

## Quy tắc chất lượng

- **Không để section trống** — ghi `[CHƯA CÓ]` nếu chưa có thông tin
- **Không tự tạo số liệu** — ví dụ có số liệu phải ghi nguồn
- **Định nghĩa học thuật phải có trích dẫn APA7** từ nguồn SSCI/Scopus hoặc văn bản pháp lý

## Xem toàn bộ thuật ngữ

→ [index.md](index.md) — Master index sắp xếp A–Z
