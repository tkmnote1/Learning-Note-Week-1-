# Matplotlib là gì?

## 1. Khái niệm

**Matplotlib** là thư viện Python dùng để vẽ biểu đồ và trực quan hóa dữ liệu.

Nếu:

```txt
NumPy dùng để xử lý mảng số, vector, ma trận
Pandas dùng để xử lý dữ liệu dạng bảng
Matplotlib dùng để vẽ biểu đồ từ dữ liệu
```

Cách import Matplotlib thường dùng:

```python
import matplotlib.pyplot as plt
```

Trong đó `plt` là tên viết tắt phổ biến của `matplotlib.pyplot`.

---

## 2. Vì sao cần Matplotlib?

Khi làm việc với dữ liệu, chỉ nhìn bảng số liệu thường rất khó thấy xu hướng.

Matplotlib giúp ta:

```txt
vẽ biểu đồ đường
vẽ biểu đồ cột
vẽ biểu đồ tròn
vẽ biểu đồ phân tán
vẽ histogram
vẽ nhiều biểu đồ để so sánh dữ liệu
trực quan hóa kết quả phân tích dữ liệu
trực quan hóa kết quả Machine Learning
```

Có thể hiểu đơn giản:

```txt
Matplotlib giúp biến dữ liệu số thành hình ảnh dễ nhìn hơn.
```

---

## 3. Biểu đồ đường

Biểu đồ đường thường dùng để thể hiện sự thay đổi của dữ liệu theo thời gian hoặc theo thứ tự.

Ví dụ:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y)
plt.show()
```

Ý nghĩa:

```txt
x là dữ liệu trên trục hoành
y là dữ liệu trên trục tung
plt.plot() dùng để vẽ biểu đồ đường
plt.show() dùng để hiển thị biểu đồ
```

---

## 4. Thêm tiêu đề và tên trục

Một biểu đồ nên có tiêu đề và tên trục để dễ hiểu.

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y)

plt.title("Simple Line Chart")
plt.xlabel("X value")
plt.ylabel("Y value")

plt.show()
```

Ý nghĩa:

```txt
plt.title()  đặt tiêu đề biểu đồ
plt.xlabel() đặt tên trục x
plt.ylabel() đặt tên trục y
```

---

## 5. Biểu đồ cột

Biểu đồ cột thường dùng để so sánh giá trị giữa các nhóm.

Ví dụ điểm của sinh viên:

```python
import matplotlib.pyplot as plt

names = ["An", "Binh", "Chi", "Dung"]
scores = [8, 9, 7, 6]

plt.bar(names, scores)

plt.title("Student Scores")
plt.xlabel("Student")
plt.ylabel("Score")

plt.show()
```

Biểu đồ cột phù hợp khi dữ liệu có dạng:

```txt
tên nhóm - giá trị
loại sản phẩm - doanh thu
sinh viên - điểm số
lớp học - số lượng sinh viên
```

---

## 6. Biểu đồ phân tán

Biểu đồ phân tán dùng để quan sát mối quan hệ giữa hai đại lượng.

Ví dụ quan hệ giữa số giờ học và điểm số:

```python
import matplotlib.pyplot as plt

hours = [1, 2, 3, 4, 5, 6]
scores = [4, 5, 6, 7, 8, 9]

plt.scatter(hours, scores)

plt.title("Study Hours and Scores")
plt.xlabel("Study Hours")
plt.ylabel("Score")

plt.show()
```

Biểu đồ phân tán thường dùng trong:

```txt
phân tích tương quan
Machine Learning
quan sát phân bố dữ liệu
phát hiện dữ liệu bất thường
```

---

## 7. Histogram

Histogram dùng để xem phân phối của dữ liệu.

Ví dụ điểm số của nhiều sinh viên:

```python
import matplotlib.pyplot as plt

scores = [5, 6, 7, 7, 8, 8, 8, 9, 10, 6, 7, 8]

plt.hist(scores, bins=5)

plt.title("Score Distribution")
plt.xlabel("Score")
plt.ylabel("Frequency")

plt.show()
```

Ý nghĩa:

```txt
plt.hist() dùng để vẽ histogram
bins là số khoảng chia dữ liệu
```

Histogram giúp trả lời các câu hỏi như:

```txt
dữ liệu tập trung ở đâu?
giá trị nào xuất hiện nhiều?
dữ liệu có lệch trái hoặc lệch phải không?
có giá trị bất thường không?
```

---

## 8. Biểu đồ tròn

Biểu đồ tròn thường dùng để thể hiện tỷ lệ phần trăm giữa các nhóm.

Ví dụ:

```python
import matplotlib.pyplot as plt

labels = ["Python", "Java", "C++", "JavaScript"]
sizes = [40, 25, 20, 15]

plt.pie(sizes, labels=labels, autopct="%1.1f%%")

plt.title("Programming Language Usage")

plt.show()
```

Ý nghĩa:

```txt
plt.pie() dùng để vẽ biểu đồ tròn
labels là tên các nhóm
autopct dùng để hiển thị phần trăm
```

Biểu đồ tròn phù hợp khi muốn thể hiện tỷ lệ thành phần trong một tổng thể.

---

## 9. Vẽ nhiều đường trên cùng một biểu đồ

Có thể vẽ nhiều đường để so sánh nhiều dữ liệu.

Ví dụ so sánh điểm Toán và Lý:

```python
import matplotlib.pyplot as plt

students = [1, 2, 3, 4, 5]
math_scores = [8, 7, 9, 6, 10]
physics_scores = [7, 8, 8, 7, 9]

plt.plot(students, math_scores, label="Math")
plt.plot(students, physics_scores, label="Physics")

plt.title("Scores Comparison")
plt.xlabel("Student")
plt.ylabel("Score")

plt.legend()
plt.show()
```

Ý nghĩa:

```txt
label dùng để đặt tên cho từng đường
plt.legend() dùng để hiển thị chú thích
```

---

## 10. Tùy chỉnh kiểu đường và điểm

Matplotlib cho phép tùy chỉnh biểu đồ.

Ví dụ:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [3, 5, 7, 9, 11]

plt.plot(x, y, marker="o", linestyle="--")

plt.title("Custom Line Chart")
plt.xlabel("X")
plt.ylabel("Y")

plt.show()
```

Một số tùy chọn thường dùng:

```txt
marker="o"     hiển thị điểm tròn
marker="s"     hiển thị điểm vuông
linestyle="-"  đường liền
linestyle="--" đường nét đứt
linestyle=":"  đường chấm
```

---

## 11. Kết hợp Matplotlib với NumPy

Matplotlib thường được dùng chung với NumPy để vẽ hàm số.

Ví dụ vẽ hàm:

```txt
y = x^2
```

Code:

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(-10, 10, 100)
y = x ** 2

plt.plot(x, y)

plt.title("Graph of y = x^2")
plt.xlabel("x")
plt.ylabel("y")

plt.show()
```

Ý nghĩa:

```txt
np.linspace(-10, 10, 100)
tạo 100 giá trị từ -10 đến 10

y = x ** 2
tính giá trị y tương ứng với từng giá trị x
```

---

## 12. Kết hợp Matplotlib với Pandas

Matplotlib thường dùng để vẽ biểu đồ từ dữ liệu trong DataFrame.

Ví dụ:

```python
import pandas as pd
import matplotlib.pyplot as plt

data = {
    "name": ["An", "Binh", "Chi", "Dung"],
    "score": [8, 9, 7, 6]
}

df = pd.DataFrame(data)

plt.bar(df["name"], df["score"])

plt.title("Student Scores")
plt.xlabel("Student")
plt.ylabel("Score")

plt.show()
```

Pandas cũng có thể gọi biểu đồ trực tiếp:

```python
df.plot(x="name", y="score", kind="bar")
plt.show()
```

---

## 13. Lưu biểu đồ thành file ảnh

Có thể lưu biểu đồ thành file PNG.

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [2, 4, 6, 8]

plt.plot(x, y)

plt.title("Simple Chart")
plt.xlabel("x")
plt.ylabel("y")

plt.savefig("chart.png")
plt.show()
```

Lưu ý:

```txt
plt.savefig("chart.png") dùng để lưu biểu đồ thành ảnh
Nên gọi savefig trước show
```

---

## 14. Ứng dụng của Matplotlib

Matplotlib được dùng nhiều trong:

```txt
Data Science
Machine Learning
thống kê dữ liệu
phân tích dữ liệu
xử lý ảnh
mô phỏng toán học
báo cáo dữ liệu
vẽ biểu đồ kết quả huấn luyện mô hình
```

Ví dụ trong Machine Learning, Matplotlib có thể dùng để vẽ:

```txt
loss theo epoch
accuracy theo epoch
biểu đồ phân phối dữ liệu
biểu đồ so sánh dự đoán và giá trị thật
```

Ví dụ vẽ loss:

```python
import matplotlib.pyplot as plt

epochs = [1, 2, 3, 4, 5]
loss = [0.9, 0.7, 0.5, 0.4, 0.3]

plt.plot(epochs, loss, marker="o")

plt.title("Training Loss")
plt.xlabel("Epoch")
plt.ylabel("Loss")

plt.show()
```

---

## 15. Matplotlib khác gì NumPy và Pandas?

Có thể phân biệt đơn giản:

```txt
NumPy      xử lý dữ liệu số dạng mảng
Pandas     xử lý dữ liệu dạng bảng
Matplotlib vẽ biểu đồ từ dữ liệu
```

Ví dụ quy trình thường gặp:

```txt
1. Dùng Pandas để đọc file CSV
2. Dùng Pandas hoặc NumPy để xử lý dữ liệu
3. Dùng Matplotlib để vẽ biểu đồ
```

Ví dụ:

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("students.csv")

plt.bar(df["name"], df["score"])
plt.show()
```

---

## 16. Một số lệnh cần nhớ

```python
import matplotlib.pyplot as plt

plt.plot()
plt.bar()
plt.scatter()
plt.hist()
plt.pie()

plt.title()
plt.xlabel()
plt.ylabel()
plt.legend()

plt.savefig()
plt.show()
```

Ý nghĩa:

```txt
plt.plot()     vẽ biểu đồ đường
plt.bar()      vẽ biểu đồ cột
plt.scatter()  vẽ biểu đồ phân tán
plt.hist()     vẽ histogram
plt.pie()      vẽ biểu đồ tròn

plt.title()    thêm tiêu đề
plt.xlabel()   thêm tên trục x
plt.ylabel()   thêm tên trục y
plt.legend()   thêm chú thích

plt.savefig()  lưu biểu đồ thành file ảnh
plt.show()     hiển thị biểu đồ
```

---

## 17. Tóm tắt

Matplotlib là thư viện Python dùng để trực quan hóa dữ liệu.

Có thể hiểu:

```txt
Matplotlib giúp biến dữ liệu số thành biểu đồ.
```

Matplotlib thường được học sau NumPy và Pandas vì:

```txt
NumPy giúp xử lý mảng số
Pandas giúp xử lý dữ liệu dạng bảng
Matplotlib giúp vẽ biểu đồ từ dữ liệu đó
```

Các loại biểu đồ cơ bản cần nhớ:

```txt
Line chart     biểu đồ đường
Bar chart      biểu đồ cột
Scatter plot   biểu đồ phân tán
Histogram      biểu đồ phân phối
Pie chart      biểu đồ tròn
```

Matplotlib rất quan trọng trong Data Science, Machine Learning và phân tích dữ liệu vì nó giúp ta nhìn thấy xu hướng, phân phối và mối quan hệ trong dữ liệu.
