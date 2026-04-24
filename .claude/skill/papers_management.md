# Papers Management — Schema, Update Rules & Filtering

## Cấu trúc thư mục

```
papers/
├── index.md                   ← Master index toàn bộ papers (luôn cập nhật)
├── credit-scoring/            ← ML/DL cho credit scoring (tổng quát)
├── explainable-ai/            ← XAI, SHAP, LIME trong ngữ cảnh ngân hàng
├── vietnam-context/           ← Nghiên cứu có dữ liệu/ngữ cảnh Việt Nam
└── framework-deployment/      ← Framework triển khai ML trong tổ chức tài chính
```

## Schema mỗi paper file

Mỗi file là `<id>.md` với YAML frontmatter bắt buộc:

```yaml
---
id: tran-2025-boosting-vietnam          # slug: author-year-keyword (lowercase, dấu gạch ngang)
authors: "Tran et al."                  # chuỗi tự do, dùng "et al." nếu ≥ 3 tác giả
year: 2025
title: "Comparative Analysis of Boosting Algorithms for Predicting Personal Default"
journal: "Cogent Economics & Finance"
indexing: Scopus                        # SSCI | SCIE | Scopus | SSCI/Scopus
quartile: Q2                            # Q1 | Q2 | Q3 | Q4 | unknown
doi: "https://doi.org/10.1080/xxxxxxx"
tags: [lightgbm, vietnam, personal-default, boosting]
relevance: high                         # high | medium | low
added_by: research-agent
date_added: "2025-04-24"               # ISO 8601
status: complete                        # complete | placeholder (thiếu thông tin)
---
```

## Cấu trúc nội dung sau frontmatter

```markdown
## Tóm tắt
[1–3 câu mô tả mục tiêu và phương pháp chính]

## Phương pháp
[Loại nghiên cứu, dataset, thuật toán/kỹ thuật, cỡ mẫu]

## Kết quả chính
[Bullet points: findings quan trọng nhất, số liệu cụ thể nếu có]

## Liên quan đến đề tài
[Giải thích rõ tại sao paper này liên quan, ở mức nào, phần nào của luận văn dùng]

## Trích dẫn APA7
[Dòng trích dẫn đầy đủ theo APA7]
```

## Quy tắc cập nhật

| Tình huống | Hành động |
|-----------|-----------|
| Paper mới được tìm thấy và vượt ngưỡng lọc | Tạo file mới + append 1 dòng vào `index.md` |
| Cần bổ sung thông tin vào paper đã có | Ghi đè file, giữ nguyên `id` và `date_added`, cập nhật `status: complete` |
| Paper trùng lặp (cùng DOI hoặc cùng tác giả+năm+tên) | Không tạo file mới — cập nhật file hiện có |
| Paper cần xóa | **Không xóa** — đổi `status: retracted` và ghi chú lý do. Chỉ xóa khi có lệnh tường minh từ người dùng |
| Di chuyển sang thư mục khác | Cập nhật đường dẫn trong `index.md`, giữ nguyên nội dung file |

## Tiêu chí lọc đầu vào

Paper chỉ được lưu khi thỏa **tất cả** điều kiện sau:

| Tiêu chí | Ngưỡng chấp nhận |
|----------|-----------------|
| Indexing | SSCI, SCIE, hoặc Scopus (ít nhất một trong ba) |
| Năm xuất bản | ≥ 2018 (ưu tiên 2019–2025) |
| Mức độ liên quan | `medium` hoặc `high` (không lưu `low`) |
| Peer-reviewed | Bắt buộc (không lưu preprint, blog, báo phổ thông) |
| Không thuộc Beall List | Kiểm tra trước khi lưu |

Nếu paper không vượt ngưỡng: báo cáo cho người dùng nhưng **không tạo file**.

## Quy tắc đặt tên file

```
<lastname-first-author>-<year>-<2-3-keyword>.md

# Ví dụ
tran-2025-boosting-vietnam.md
gramegna-giudici-2021-shap-lime.md
anon-2023-ml-credit-risk.md          # dùng "anon" khi không biết tác giả
```

## Quy tắc chọn thư mục con

| Nội dung chính của paper | Thư mục |
|--------------------------|---------|
| ML/DL methods cho credit scoring (tổng quát) | `credit-scoring/` |
| XAI, SHAP, LIME, interpretability | `explainable-ai/` |
| Nghiên cứu dùng dữ liệu VN hoặc thị trường mới nổi | `vietnam-context/` |
| Framework, governance, deployment ML trong ngân hàng | `framework-deployment/` |
| Có thể thuộc nhiều nhóm | Chọn nhóm **liên quan nhất**; ghi tag đầy đủ |
