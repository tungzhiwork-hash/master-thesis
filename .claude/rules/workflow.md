# Workflow Phối Hợp Giữa Các Agent

## Sơ đồ điều phối

```
Yêu cầu của người dùng
         │
         ▼
┌─────────────────┐
│ Structure Agent │  ← Luôn biết bức tranh tổng thể
│ (Orchestrator)  │
└────────┬────────┘
         │ Phân loại yêu cầu
         ▼
┌────────────────────────────────────────────┐
│                                            │
│  Tìm tài liệu?  →  Research Agent         │
│                         │                  │
│  Viết nội dung? ←───────┤                  │
│       │         →  Writing Agent           │
│       │                 │                  │
│  Phân tích data?        │                  │
│       │         →  Analysis Agent          │
│       │                 │                  │
│  Review chất lượng? ←───┘                  │
│                 →  Review Agent            │
│                                            │
└────────────────────────────────────────────┘
         │
         ▼
    Output cuối cùng
    (Markdown / Python / Bảng / Draft văn bản)
```

## Quy trình chuẩn cho một phần luận văn mới

| Bước | Agent | Nhiệm vụ |
|------|-------|----------|
| 1 | Research Agent | Tìm & tổng hợp tài liệu liên quan |
| 2 | Writing Agent | Soạn thảo nội dung có trích dẫn |
| 3 | Analysis Agent | Bổ sung phân tích / code nếu cần |
| 4 | Review Agent | Phản biện, chỉ ra lỗ hổng |
| 5 | Writing Agent | Chỉnh sửa theo phản biện |
| 6 | Structure Agent | Cập nhật tracker, kiểm tra nhất quán |

## Bắt đầu mỗi session

Luôn bắt đầu bằng:
```
[STRUCTURE] Cập nhật trạng thái để đồng bộ tiến độ
```
