# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600141 - tan2610.og@gmail.com  
**Name:** Nguyen Cong Nhat Tan
**Date:** 15/4/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 10 | Agent nhận định đúng đắn dựa trên các thông số sản phẩm thông thường. |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 0 | Agent bị đánh lừa ngay lập tức bởi outlier có giá trị quá sai lệch (fraud). |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Tại vì dữ liệu rác (Garbage Data) có chứa các giá trị ngoại lai (outliers) hoặc các giá trị không hợp lệ (như Nuclear Reactor với giá phi thực tế là $999999). Khi hệ thống AI Agent quét qua dũ liệu mà không có cơ chế Validation, nó sẽ tiếp thu và tư vấn các kết quả tồi tệ này cho người dùng. Điều này thể hiện rất rõ sự nguy hiểm của các null values, wrong data types, hoặc false categories trong việc phá hỏng hoàn toàn logic và độ an toàn của một tính năng có sử dụng AI.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Hoàn toàn đồng ý. Câu nói "Garbage In, Garbage Out" luôn đúng đối với AI. Ngay cả khi Agent có một System Prompt xuất sắc để suy luận logic, nếu context được truyền vào là dữ liệu rác, nó bắt buộc phải trả ra kết quả vô nghĩa hoặc nguy hiểm. Việc có một Pipeline ETL chuẩn để làm sạch dữ liệu là ưu tiên cực kỳ sống còn.
