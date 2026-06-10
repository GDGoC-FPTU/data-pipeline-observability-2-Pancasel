# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600952
**Name:** Đỗ Quốc An
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | The agent correctly identified the relevant product and price. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | The agent picked an irrelevant/invalid outlier due to poor data quality. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi sử dụng dữ liệu rác (Garbage Data), AI Agent đã trả lời sai vì thiếu quá trình làm sạch và chuẩn hóa dữ liệu. Dữ liệu rác chứa các bản ghi không hợp lệ, đặc biệt là các giá trị ngoại lai (outlier) với mức giá cực kỳ ảo (ví dụ $999999 cho Nuclear Reactor). Do thuật toán tìm kiếm của Agent đơn thuần chọn sản phẩm có giá trị cao nhất thỏa mãn điều kiện chuỗi (string matching) mà không thể tự nhận biết tính vô lý của dữ liệu, nó dễ dàng bị đánh lừa bởi dữ liệu lỗi, dẫn đến kết quả trả về sai lệch hoàn toàn so với thực tế.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Hoàn toàn đồng ý.

Cho dù mô hình AI có thông minh hay Prompt có phức tạp đến đâu, nếu dữ liệu đầu vào là "rác" (Garbage In), thì đầu ra chắc chắn sẽ là "rác" (Garbage Out). Việc xây dựng ETL Pipeline để extract, validate, transform và load dữ liệu chuẩn là bước nền tảng sống còn để AI hoạt động chính xác.
