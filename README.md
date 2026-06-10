[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112834&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** student@example.com
**Name:** Nguyen Van A

---

## Mo ta

Trong bài Lab này, em đã xây dựng một ETL Pipeline tự động bằng Python. Quá trình bao gồm việc trích xuất dữ liệu từ tệp JSON, kiểm tra tính hợp lệ của dữ liệu (loại bỏ giá trị âm và category rỗng), chuẩn hóa category thành Title Case và tính giá đã giảm 10%, sau đó lưu kết quả đã làm sạch ra tệp CSV. Cuối cùng, em chạy mô phỏng AI Agent để kiểm chứng ảnh hưởng của dữ liệu sạch và dữ liệu rác đến độ chính xác của Agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Mô phỏng AI Agent với dữ liệu Clean và Garbage
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Kết quả ETL Pipeline: Xử lý thành công 3 bản ghi (valid) và loại bỏ 2 bản ghi (errors). Dữ liệu sau xử lý được lưu vào file `processed_data.csv`.

Kết quả Stress Test:
- Clean data: Agent hoạt động chính xác (chọn Laptop).
- Garbage data: Agent hoạt động sai lệch và bị đánh lừa bởi dữ liệu lỗi (chọn Nuclear Reactor).
