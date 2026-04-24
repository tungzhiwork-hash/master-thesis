# Hệ thống Agent Hỗ trợ Luận văn Thạc sĩ

## Cấu trúc tài liệu

```
.claude/
├── agent/
│   ├── research.md           — 🔬 Tìm kiếm & tổng hợp tài liệu học thuật
│   ├── writing.md            — ✍️  Soạn thảo nội dung theo chuẩn UEH
│   ├── analysis.md           — 📊 Phân tích dữ liệu, ML pipeline, Python code
│   ├── review.md             — 🔍 Phản biện theo rubric hội đồng UEH
│   ├── structure.md          — 🗂️  Orchestrator: quản lý tiến độ & nhất quán
│   └── glossary.md           — 📖 Tra cứu & lưu trữ thuật ngữ học thuật
├── skill/
│   ├── apa7_citation.md      — Chuẩn trích dẫn APA 7
│   ├── ml_pipeline.md        — Pipeline ML chuẩn cho credit scoring
│   ├── academic_vocabulary.md — Bảng từ vựng học thuật tiếng Việt
│   ├── technical_env.md      — Môi trường Python & thư viện
│   ├── papers_management.md  — Schema & quy tắc kho papers
│   └── glossary_management.md — Schema & quy tắc kho glossary
└── rules/
    ├── project_context.md    — Bối cảnh đề tài & thông tin học viên
    ├── general_principles.md — Nguyên tắc chung cho mọi agent
    ├── workflow.md           — Quy trình phối hợp giữa các agent
    ├── invocation.md         — Cách gọi agent bằng prefix
    └── special_notes.md      — Lưu ý đặc biệt về dữ liệu & giải pháp
```

## Cách sử dụng nhanh

```
[RESEARCH]  Tìm tài liệu / literature review
[WRITE]     Soạn thảo / paraphrase / tích hợp trích dẫn
[ANALYSIS]  Code Python / so sánh mô hình / giải thích kết quả
[REVIEW]    Phản biện / kiểm tra logic / rubric UEH
[STRUCTURE] Tiến độ / outline / còn thiếu gì
[GLOSSARY]  Tra cứu / thêm / giải thích thuật ngữ
```

## Kho dữ liệu

```
papers/                        ← 12 nghiên cứu đã tổng hợp (credit scoring, XAI, Vietnam...)
thesis-glossary/               ← Từ điển thuật ngữ học thuật (A–Z)
```

Nếu không có prefix, Claude tự chọn agent phù hợp dựa trên nội dung yêu cầu.
