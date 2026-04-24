# Glossary Management — Schema & Phân loại

## Cấu trúc thư mục

```
thesis-glossary/
├── README.md                      ← Hướng dẫn sử dụng
├── index.md                       ← Master index toàn bộ từ khóa (A–Z)
├── finance-banking/               ← Tài chính – Ngân hàng
├── ai-machine-learning/           ← AI – Machine Learning
├── statistics-econometrics/       ← Thống kê – Kinh tế lượng
├── tech-management/               ← Quản trị Công nghệ
└── regulatory-legal/              ← Pháp lý – Quy định
```

**Quy tắc đặt tên file:** lowercase, dấu gạch ngang, không dấu tiếng Việt.
Ví dụ: `non-performing-loan.md`, `xgboost.md`, `basel-iii.md`

## Tiêu chí phân loại vào thư mục con

| Thư mục | Phân loại khi |
|---------|---------------|
| `finance-banking/` | Khái niệm xuất phát từ ngành tài chính, ngân hàng, tín dụng. VD: NPL, LTV, credit score, collateral, provision |
| `ai-machine-learning/` | Thuật toán, kỹ thuật, metrics thuộc ML/DL/AI. VD: XGBoost, SHAP, AUC-ROC, SMOTE, overfitting, feature importance |
| `statistics-econometrics/` | Phương pháp thống kê và kinh tế lượng. VD: logistic regression, panel data, Cronbach Alpha, EFA, SEM |
| `tech-management/` | Khái niệm quản trị, chiến lược, mô hình tổ chức. VD: digital transformation, technology adoption, framework triển khai |
| `regulatory-legal/` | Quy định pháp lý, chuẩn mực quốc tế và trong nước. VD: Basel III, Thông tư 11/2021/TT-NHNN |

Nếu một term thuộc nhiều nhóm: **ưu tiên thư mục gốc** của khái niệm và ghi `related_terms` dẫn sang các file liên quan.

## Schema bắt buộc cho mỗi file thuật ngữ

```markdown
---
term_en: ""          # Tên tiếng Anh đầy đủ
term_abbr: ""        # Viết tắt (nếu không có thì để "")
term_vi: ""          # Tên tiếng Việt chuẩn dùng trong luận văn
category: ""         # finance-banking | ai-machine-learning | statistics-econometrics | tech-management | regulatory-legal
related_terms: []    # Danh sách slug của các term liên quan
date_added: ""       # YYYY-MM-DD
last_updated: ""     # YYYY-MM-DD
---

## Định nghĩa học thuật

[Định nghĩa chính xác từ tài liệu học thuật uy tín. Bắt buộc có trích dẫn APA7
ngay cuối câu. Ưu tiên nguồn SSCI/Scopus hoặc văn bản pháp lý chính thức.]

## Định nghĩa bằng lời của tôi

[Diễn giải lại bằng ngôn ngữ tự nhiên, không cần học thuật. Viết như giải thích
cho người chưa biết gì về lĩnh vực này. Không cần trích dẫn.]

## Ngữ cảnh trong luận văn

[Khái niệm này liên quan đến phần nào của đề tài? Đóng vai trò gì trong lập luận?
Xuất hiện ở chương nào?]

## Ví dụ thực tế

[Ví dụ cụ thể, ưu tiên từ thị trường Việt Nam hoặc ngữ cảnh ngân hàng thương mại.
Nếu có số liệu thực, ghi rõ nguồn.]

## Câu dùng trong luận văn (mẫu)

> "[Term] đóng vai trò then chốt trong việc [mục đích], đặc biệt trong bối cảnh
> [ngữ cảnh VN] ([Tác giả, Năm])."

## Nguồn tham khảo

- [Nguồn 1 — APA7 đầy đủ]
- [Nguồn 2 — APA7 đầy đủ]
```

Nếu chưa có thông tin một section: ghi `[CHƯA CÓ]`, **không được để trống**.

## Schema của index.md

```markdown
# Master Index — Thesis Glossary

Cập nhật lần cuối: YYYY-MM-DD | Tổng số thuật ngữ: N

## A
| Thuật ngữ (EN) | Viết tắt | Tiếng Việt | Danh mục | File |
|----------------|----------|------------|----------|------|
| Area Under Curve | AUC | Diện tích dưới đường cong | ai-machine-learning | [auc-roc.md](ai-machine-learning/auc-roc.md) |

## B
| Basel III | — | Hiệp ước Basel III | regulatory-legal | [basel-iii.md](regulatory-legal/basel-iii.md) |
```

Sắp xếp theo alphabet của tên tiếng Anh. Mỗi chữ cái là một heading `##`.
