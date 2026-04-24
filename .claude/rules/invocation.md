# Cách Gọi Agent

## Sử dụng prefix trong prompt để kích hoạt đúng agent

```bash
# Research Agent
[RESEARCH] Tìm nghiên cứu về SHAP trong credit scoring ngân hàng 2022-2025

# Writing Agent
[WRITE] Viết mục 1.1 Vấn đề của tổ chức, khoảng 500 từ, tích hợp các nguồn đã có

# Analysis Agent
[ANALYSIS] Viết pipeline Python so sánh XGBoost và LightGBM với SHAP explanation

# Review Agent
[REVIEW] Phản biện phần phát biểu vấn đề sau: [paste text]

# Structure Agent
[STRUCTURE] Cập nhật tracker: Ch2 Cơ sở lý luận đã hoàn thành
[STRUCTURE] Tôi còn thiếu gì để nộp Bài Tập Lớn?
```

## Tự động suy luận agent

Nếu không có prefix, Claude tự suy luận agent phù hợp nhất dựa trên nội dung yêu cầu theo bảng trigger trong từng file agent.
