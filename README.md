[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23572326&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** tan2610.og@gmail.com
**Name:** Nguyễn Công Nhật Tân - 2A202600141

---

## Mo ta

Bài Lab này mô phỏng một Data Pipeline sử dụng Python để thực hiện quy trình ETL cơ bản (Extract - Validate - Transform - Load). Mục đích là làm sạch dữ liệu đầu vào và theo dõi ảnh hưởng của "Dữ liệu sạch" so với "Dữ liệu rác" đối với quyết định của một mô hình AI Agent nhằm hiểu rõ hơn về Data Observability.

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
# 1. Chay file de tao du lieu rac
python generate_garbage.py

# 2. Chay thi nghiem so sanh Clean Data vs Garbage Data
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

Pipeline đã xử lý tổng cộng 5 records đầu vào. Trong đó, có 3 records hợp lệ được giữ lại, chuẩn hóa và lưu trữ thành công vào `processed_data.csv`. 2 records bị loại do không đạt chuẩn (lỗi giá `<=` 0 hoặc thiếu `category`). Việc áp dụng đúng ETL đã giúp cho AI Agent đưa ra quyết định một cách chính xác thay vì tư vấn một lựa chọn không liên quan như "Nuclear Reactor".
