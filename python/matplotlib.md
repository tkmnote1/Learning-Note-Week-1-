# Matplotlib trong Python

## 1. Matplotlib là gì?

**Matplotlib** là thư viện Python dùng để **vẽ biểu đồ** và **trực quan hóa dữ liệu**.

Nếu:

```txt
NumPy      dùng để xử lý mảng số, vector, ma trận
Pandas     dùng để xử lý dữ liệu dạng bảng
Matplotlib dùng để vẽ biểu đồ từ dữ liệu
```

Cách import Matplotlib thường dùng:

```python
import matplotlib.pyplot as plt
```


Ví dụ đầu tiên:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y)
plt.show()
```

Kết quả là một biểu đồ đường đơn giản.

Có thể hiểu ngắn gọn:

```txt
Matplotlib giúp biến dữ liệu số thành hình ảnh trực quan.
```

---

## 2. Vì sao cần Matplotlib?

Khi làm việc với dữ liệu, nếu chỉ nhìn bảng số thì rất khó phát hiện:

```txt
xu hướng tăng giảm
sự phân bố dữ liệu
mối quan hệ giữa các biến
giá trị bất thường
sự khác biệt giữa các nhóm
kết quả huấn luyện mô hình
```

Matplotlib giúp ta:

```txt
vẽ biểu đồ đường
vẽ biểu đồ cột
vẽ biểu đồ phân tán
vẽ histogram
vẽ biểu đồ tròn
vẽ nhiều đường trên cùng biểu đồ
lưu biểu đồ thành ảnh
trực quan hóa dữ liệu trong Data Science và Machine Learning
```

Ví dụ trong Machine Learning, Matplotlib thường dùng để vẽ:

```txt
training loss
validation loss
accuracy
confusion matrix
phân phối dữ liệu
so sánh giá trị dự đoán và giá trị thật
```

---

## 3. Cấu trúc cơ bản khi vẽ biểu đồ

Một biểu đồ Matplotlib cơ bản thường có dạng:

```python
import matplotlib.pyplot as plt

plt.plot(x, y)

plt.title("Title")
plt.xlabel("X label")
plt.ylabel("Y label")

plt.show()
```

Ý nghĩa:

```txt
plt.plot()   vẽ biểu đồ đường
plt.title()  đặt tiêu đề biểu đồ
plt.xlabel() đặt tên trục x
plt.ylabel() đặt tên trục y
plt.show()   hiển thị biểu đồ
```

Ví dụ:

```python
import matplotlib.pyplot as plt

days = [1, 2, 3, 4, 5]
temperature = [30, 31, 33, 32, 34]

plt.plot(days, temperature)

plt.title("Temperature by Day")
plt.xlabel("Day")
plt.ylabel("Temperature")

plt.show()
```

---

## 4. Figure và Axes là gì?

Trong Matplotlib có hai khái niệm quan trọng:

```txt
Figure: toàn bộ khung hình chứa biểu đồ
Axes: vùng biểu đồ cụ thể bên trong Figure
```

Có thể hiểu:

```txt
Figure giống như tờ giấy.
Axes giống như vùng vẽ biểu đồ trên tờ giấy đó.
```

Cách vẽ cơ bản bằng `plt`:

```python
plt.plot(x, y)
plt.show()
```

Cách vẽ rõ ràng hơn bằng `fig, ax`:

```python
import matplotlib.pyplot as plt

fig, ax = plt.subplots()

ax.plot([1, 2, 3], [2, 4, 6])
ax.set_title("Simple Chart")
ax.set_xlabel("x")
ax.set_ylabel("y")

plt.show()
```

Trong thực tế, khi biểu đồ phức tạp hơn, cách dùng `fig, ax` thường dễ quản lý hơn.

---

## 5. Biểu đồ đường

Biểu đồ đường dùng để thể hiện sự thay đổi của dữ liệu theo thời gian hoặc theo thứ tự.

Ví dụ:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

plt.plot(x, y)

plt.title("Line Chart")
plt.xlabel("x")
plt.ylabel("y")

plt.show()
```

Biểu đồ đường phù hợp với:

```txt
dữ liệu theo thời gian
nhiệt độ theo ngày
doanh thu theo tháng
loss theo epoch
accuracy theo epoch
giá cổ phiếu theo ngày
```

Ví dụ vẽ loss trong Machine Learning:

```python
import matplotlib.pyplot as plt

epochs = [1, 2, 3, 4, 5]
loss = [0.9, 0.7, 0.55, 0.43, 0.35]

plt.plot(epochs, loss)

plt.title("Training Loss")
plt.xlabel("Epoch")
plt.ylabel("Loss")

plt.show()
```

---

## 6. Tùy chỉnh đường vẽ

Matplotlib cho phép tùy chỉnh marker, kiểu đường, độ dày đường.

Ví dụ:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [3, 5, 7, 9, 11]

plt.plot(x, y, marker="o", linestyle="--", linewidth=2)

plt.title("Custom Line Chart")
plt.xlabel("x")
plt.ylabel("y")

plt.show()
```

Một số tùy chọn thường dùng:

```txt
marker="o"      điểm tròn
marker="s"      điểm vuông
marker="*"      điểm ngôi sao

linestyle="-"   đường liền
linestyle="--"  đường nét đứt
linestyle=":"   đường chấm

linewidth=2     độ dày đường
```

---

## 7. Vẽ nhiều đường trên cùng một biểu đồ

Có thể vẽ nhiều đường để so sánh nhiều tập dữ liệu.

Ví dụ:

```python
import matplotlib.pyplot as plt

epochs = [1, 2, 3, 4, 5]

train_loss = [0.9, 0.7, 0.5, 0.4, 0.3]
val_loss = [1.0, 0.8, 0.65, 0.6, 0.58]

plt.plot(epochs, train_loss, marker="o", label="Training Loss")
plt.plot(epochs, val_loss, marker="s", label="Validation Loss")

plt.title("Training and Validation Loss")
plt.xlabel("Epoch")
plt.ylabel("Loss")

plt.legend()
plt.show()
```

Ý nghĩa:

```txt
label dùng để đặt tên cho từng đường
plt.legend() dùng để hiển thị chú thích
```

Biểu đồ này thường dùng khi đánh giá mô hình Machine Learning.

---

## 8. Biểu đồ cột

Biểu đồ cột dùng để so sánh giá trị giữa các nhóm.

Ví dụ:

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

Biểu đồ cột phù hợp với:

```txt
điểm của sinh viên
doanh thu từng tháng
số lượng sản phẩm bán ra
số sinh viên từng lớp
so sánh kết quả giữa các mô hình
```

Ví dụ so sánh độ chính xác của các mô hình:

```python
import matplotlib.pyplot as plt

models = ["Linear Regression", "Random Forest", "XGBoost"]
scores = [0.72, 0.85, 0.88]

plt.bar(models, scores)

plt.title("Model Performance")
plt.xlabel("Model")
plt.ylabel("Score")

plt.show()
```

---

## 9. Biểu đồ cột ngang

Biểu đồ cột ngang dùng khi tên nhóm dài hoặc muốn dễ đọc hơn.

```python
import matplotlib.pyplot as plt

features = ["study_hours", "attendance", "homework_score", "previous_score"]
importance = [0.4, 0.2, 0.25, 0.15]

plt.barh(features, importance)

plt.title("Feature Importance")
plt.xlabel("Importance")
plt.ylabel("Feature")

plt.show()
```

Lệnh:

```python
plt.barh()
```

dùng để vẽ biểu đồ cột ngang.

---

## 10. Biểu đồ phân tán

Biểu đồ phân tán dùng để quan sát mối quan hệ giữa hai đại lượng.

Ví dụ:

```python
import matplotlib.pyplot as plt

study_hours = [1, 2, 3, 4, 5, 6]
scores = [4, 5, 6, 7, 8, 9]

plt.scatter(study_hours, scores)

plt.title("Study Hours and Scores")
plt.xlabel("Study Hours")
plt.ylabel("Score")

plt.show()
```

Biểu đồ phân tán phù hợp với:

```txt
phân tích tương quan
quan sát phân bố dữ liệu
phát hiện outlier
Machine Learning
hồi quy tuyến tính
```

Ví dụ trong hồi quy tuyến tính:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y_true = [2, 4, 5, 4, 5]
y_pred = [2.2, 3.8, 4.5, 4.7, 5.1]

plt.scatter(x, y_true, label="True Data")
plt.plot(x, y_pred, label="Prediction")

plt.title("Linear Regression Prediction")
plt.xlabel("x")
plt.ylabel("y")

plt.legend()
plt.show()
```

---

## 11. Histogram

Histogram dùng để xem phân phối của dữ liệu.

Ví dụ:

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

Histogram giúp trả lời:

```txt
dữ liệu tập trung ở đâu?
giá trị nào xuất hiện nhiều?
dữ liệu có phân phối đều không?
dữ liệu có lệch trái hoặc lệch phải không?
có giá trị bất thường không?
```

Ví dụ với dữ liệu ngẫu nhiên:

```python
import numpy as np
import matplotlib.pyplot as plt

data = np.random.randn(1000)

plt.hist(data, bins=30)

plt.title("Normal Distribution")
plt.xlabel("Value")
plt.ylabel("Frequency")

plt.show()
```

---

## 12. Biểu đồ tròn

Biểu đồ tròn dùng để thể hiện tỷ lệ phần trăm giữa các nhóm.

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

Không nên dùng biểu đồ tròn khi có quá nhiều nhóm vì sẽ khó đọc.

---

## 13. Boxplot

Boxplot dùng để quan sát phân phối dữ liệu và phát hiện giá trị bất thường.

Ví dụ:

```python
import matplotlib.pyplot as plt

scores = [5, 6, 7, 8, 8, 9, 10, 10, 4, 3, 100]

plt.boxplot(scores)

plt.title("Score Boxplot")
plt.ylabel("Score")

plt.show()
```

Boxplot giúp quan sát:

```txt
median
quartile
khoảng phân bố chính của dữ liệu
outlier
```

Boxplot thường dùng trong phân tích dữ liệu để phát hiện dữ liệu bất thường.

---

## 14. Vẽ hàm số với NumPy và Matplotlib

Matplotlib thường dùng chung với NumPy để vẽ hàm số.

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
tính giá trị y tương ứng với từng x
```

Ví dụ vẽ hàm sin:

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0, 2 * np.pi, 100)
y = np.sin(x)

plt.plot(x, y)

plt.title("Graph of y = sin(x)")
plt.xlabel("x")
plt.ylabel("sin(x)")

plt.show()
```

---

## 15. Vẽ nhiều hàm số

Ví dụ vẽ `sin(x)` và `cos(x)` trên cùng biểu đồ:

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0, 2 * np.pi, 100)

y1 = np.sin(x)
y2 = np.cos(x)

plt.plot(x, y1, label="sin(x)")
plt.plot(x, y2, label="cos(x)")

plt.title("Sine and Cosine")
plt.xlabel("x")
plt.ylabel("y")

plt.legend()
plt.show()
```

---

## 16. Thêm lưới vào biểu đồ

Lưới giúp biểu đồ dễ đọc hơn.

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(-10, 10, 100)
y = x ** 2

plt.plot(x, y)

plt.title("Graph of y = x^2")
plt.xlabel("x")
plt.ylabel("y")

plt.grid(True)

plt.show()
```

Lệnh:

```python
plt.grid(True)
```

dùng để bật lưới.

---

## 17. Giới hạn trục

Có thể giới hạn miền hiển thị của trục x và y.

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(-10, 10, 100)
y = x ** 2

plt.plot(x, y)

plt.xlim(-5, 5)
plt.ylim(0, 30)

plt.title("Limited Axis")
plt.xlabel("x")
plt.ylabel("y")

plt.show()
```

Ý nghĩa:

```txt
plt.xlim(-5, 5) giới hạn trục x từ -5 đến 5
plt.ylim(0, 30) giới hạn trục y từ 0 đến 30
```

---

## 18. Lưu biểu đồ thành file ảnh

Có thể lưu biểu đồ thành file ảnh.

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
Nên gọi plt.savefig() trước plt.show().
```

Có thể lưu với độ phân giải cao hơn:

```python
plt.savefig("chart.png", dpi=300)
```

Một số định dạng thường dùng:

```txt
.png
.jpg
.pdf
.svg
```

---

## 19. Kích thước biểu đồ

Có thể chỉnh kích thước biểu đồ bằng `figsize`.

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [2, 4, 6, 8]

plt.figure(figsize=(8, 5))

plt.plot(x, y)

plt.title("Chart with Custom Size")
plt.xlabel("x")
plt.ylabel("y")

plt.show()
```

Ý nghĩa:

```txt
figsize=(8, 5)
chiều rộng 8 inch
chiều cao 5 inch
```

---

## 20. Subplot là gì?

Subplot dùng để vẽ nhiều biểu đồ trong cùng một Figure.

Ví dụ vẽ hai biểu đồ cạnh nhau:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y1 = [2, 4, 6, 8]
y2 = [1, 4, 9, 16]

plt.subplot(1, 2, 1)
plt.plot(x, y1)
plt.title("Chart 1")

plt.subplot(1, 2, 2)
plt.plot(x, y2)
plt.title("Chart 2")

plt.show()
```

Ý nghĩa:

```txt
plt.subplot(1, 2, 1)
1 dòng, 2 cột, biểu đồ thứ 1

plt.subplot(1, 2, 2)
1 dòng, 2 cột, biểu đồ thứ 2
```

Cách dùng `fig, ax`:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y1 = [2, 4, 6, 8]
y2 = [1, 4, 9, 16]

fig, axes = plt.subplots(1, 2, figsize=(10, 4))

axes[0].plot(x, y1)
axes[0].set_title("Chart 1")

axes[1].plot(x, y2)
axes[1].set_title("Chart 2")

plt.show()
```

---

## 21. Kết hợp Matplotlib với Pandas

Pandas dùng để xử lý dữ liệu dạng bảng, Matplotlib dùng để vẽ biểu đồ từ dữ liệu đó.

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

Pandas cũng có thể vẽ nhanh bằng `.plot()`:

```python
df.plot(x="name", y="score", kind="bar")
plt.show()
```

Một số kiểu biểu đồ trong Pandas:

```python
df.plot(kind="line")
df.plot(kind="bar")
df.plot(kind="hist")
df.plot(kind="scatter", x="age", y="score")
```

---

## 22. Vẽ dữ liệu từ file CSV

Ví dụ file `students.csv`:

```csv
name,age,score
An,20,8.5
Binh,21,9.0
Chi,19,7.5
Dung,22,6.0
```

Code đọc file và vẽ biểu đồ:

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("students.csv")

plt.bar(df["name"], df["score"])

plt.title("Student Scores")
plt.xlabel("Student")
plt.ylabel("Score")

plt.show()
```

---

## 23. Vẽ biểu đồ từ dữ liệu Machine Learning

Ví dụ vẽ training loss và validation loss:

```python
import matplotlib.pyplot as plt

epochs = [1, 2, 3, 4, 5, 6]

train_loss = [0.95, 0.8, 0.65, 0.5, 0.4, 0.32]
val_loss = [1.0, 0.86, 0.72, 0.64, 0.61, 0.60]

plt.plot(epochs, train_loss, marker="o", label="Training Loss")
plt.plot(epochs, val_loss, marker="s", label="Validation Loss")

plt.title("Training vs Validation Loss")
plt.xlabel("Epoch")
plt.ylabel("Loss")

plt.legend()
plt.grid(True)
plt.show()
```

Ý nghĩa:

```txt
Nếu training loss giảm nhưng validation loss không giảm hoặc tăng,
mô hình có thể đang bị overfitting.
```

Ví dụ vẽ accuracy:

```python
import matplotlib.pyplot as plt

epochs = [1, 2, 3, 4, 5]

train_acc = [0.60, 0.70, 0.78, 0.84, 0.88]
val_acc = [0.58, 0.68, 0.74, 0.76, 0.77]

plt.plot(epochs, train_acc, marker="o", label="Training Accuracy")
plt.plot(epochs, val_acc, marker="s", label="Validation Accuracy")

plt.title("Training vs Validation Accuracy")
plt.xlabel("Epoch")
plt.ylabel("Accuracy")

plt.legend()
plt.grid(True)
plt.show()
```

---

## 24. Vẽ so sánh giá trị thật và giá trị dự đoán

Trong bài toán hồi quy, ta thường muốn so sánh giá trị thật và giá trị mô hình dự đoán.

```python
import matplotlib.pyplot as plt

y_true = [10, 20, 30, 40, 50]
y_pred = [12, 18, 33, 37, 52]

plt.plot(y_true, marker="o", label="True Values")
plt.plot(y_pred, marker="s", label="Predicted Values")

plt.title("True vs Predicted Values")
plt.xlabel("Sample")
plt.ylabel("Value")

plt.legend()
plt.grid(True)
plt.show()
```

Hoặc dùng scatter plot:

```python
import matplotlib.pyplot as plt

y_true = [10, 20, 30, 40, 50]
y_pred = [12, 18, 33, 37, 52]

plt.scatter(y_true, y_pred)

plt.title("True vs Predicted Scatter")
plt.xlabel("True Values")
plt.ylabel("Predicted Values")

plt.show()
```

Nếu mô hình dự đoán tốt, các điểm thường nằm gần đường chéo `y = x`.

---

## 25. Vẽ confusion matrix cơ bản

Confusion matrix thường dùng trong bài toán phân loại.

Ví dụ ma trận nhầm lẫn:

```python
import numpy as np
import matplotlib.pyplot as plt

cm = np.array([
    [8, 2],
    [1, 9]
])

plt.imshow(cm)

plt.title("Confusion Matrix")
plt.xlabel("Predicted Label")
plt.ylabel("True Label")

plt.colorbar()
plt.show()
```

Nếu muốn thêm số vào từng ô:

```python
import numpy as np
import matplotlib.pyplot as plt

cm = np.array([
    [8, 2],
    [1, 9]
])

plt.imshow(cm)
plt.colorbar()

for i in range(cm.shape[0]):
    for j in range(cm.shape[1]):
        plt.text(j, i, cm[i, j], ha="center", va="center")

plt.title("Confusion Matrix")
plt.xlabel("Predicted Label")
plt.ylabel("True Label")

plt.show()
```

---

## 26. Matplotlib trong Data Science

Trong Data Science, Matplotlib thường dùng để:

```txt
xem phân phối dữ liệu
so sánh các nhóm dữ liệu
phát hiện dữ liệu bất thường
quan sát quan hệ giữa các biến
trực quan hóa kết quả phân tích
trình bày báo cáo dữ liệu
```

Ví dụ quy trình cơ bản:

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("data.csv")

print(df.head())
print(df.info())
print(df.describe())

plt.hist(df["score"], bins=10)
plt.title("Score Distribution")
plt.xlabel("Score")
plt.ylabel("Frequency")
plt.show()
```

---

## 27. Matplotlib khác gì NumPy và Pandas?

Phân biệt đơn giản:

```txt
NumPy:
Xử lý dữ liệu số dạng mảng, vector, ma trận.

Pandas:
Xử lý dữ liệu dạng bảng, hàng, cột, file CSV, Excel.

Matplotlib:
Vẽ biểu đồ và trực quan hóa dữ liệu.
```

Quy trình thường gặp:

```txt
1. Dùng Pandas để đọc dữ liệu từ CSV hoặc Excel.
2. Dùng Pandas hoặc NumPy để xử lý dữ liệu.
3. Dùng Matplotlib để vẽ biểu đồ.
```

Ví dụ:

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("students.csv")

plt.bar(df["name"], df["score"])

plt.title("Student Scores")
plt.xlabel("Student")
plt.ylabel("Score")

plt.show()
```

---

## 28. Một số lỗi thường gặp khi học Matplotlib

### Lỗi 1: Quên `plt.show()`

Sai:

```python
import matplotlib.pyplot as plt

plt.plot([1, 2, 3], [2, 4, 6])
```

Trong một số môi trường, biểu đồ có thể không hiện.

Đúng:

```python
plt.plot([1, 2, 3], [2, 4, 6])
plt.show()
```

---

### Lỗi 2: Độ dài x và y không bằng nhau

Sai:

```python
x = [1, 2, 3]
y = [2, 4]

plt.plot(x, y)
plt.show()
```

Lỗi vì `x` có 3 phần tử, `y` có 2 phần tử.

Đúng:

```python
x = [1, 2, 3]
y = [2, 4, 6]

plt.plot(x, y)
plt.show()
```

---

### Lỗi 3: Chữ trên trục x bị chồng lên nhau

Nếu tên quá dài, có thể xoay nhãn trục x:

```python
plt.xticks(rotation=45)
```

Ví dụ:

```python
import matplotlib.pyplot as plt

names = ["Very Long Name 1", "Very Long Name 2", "Very Long Name 3"]
scores = [8, 9, 7]

plt.bar(names, scores)
plt.xticks(rotation=45)

plt.show()
```

---

### Lỗi 4: Lưu biểu đồ sau `plt.show()`

Nên lưu trước khi show:

```python
plt.savefig("chart.png")
plt.show()
```

Không nên viết:

```python
plt.show()
plt.savefig("chart.png")
```

Vì đôi khi file lưu ra có thể bị trắng.

---

### Lỗi 5: Quên `legend`

Nếu vẽ nhiều đường mà không có chú thích, biểu đồ khó hiểu.

```python
plt.plot(x, y1, label="Line 1")
plt.plot(x, y2, label="Line 2")
plt.legend()
plt.show()
```

---

### Lỗi 6: Biểu đồ quá nhỏ

Có thể chỉnh kích thước:

```python
plt.figure(figsize=(10, 6))
```

---

## 29. Bài tập luyện tập

### Bài 1

Tạo hai list:

```python
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]
```

Yêu cầu:

```txt
vẽ biểu đồ đường
thêm title
thêm xlabel
thêm ylabel
hiển thị biểu đồ
```

---

### Bài 2

Tạo dữ liệu điểm sinh viên:

```python
names = ["An", "Binh", "Chi", "Dung"]
scores = [8, 9, 7, 6]
```

Yêu cầu:

```txt
vẽ biểu đồ cột
đặt tiêu đề Student Scores
đặt tên trục x là Student
đặt tên trục y là Score
```

---

### Bài 3

Tạo dữ liệu:

```python
study_hours = [1, 2, 3, 4, 5, 6]
scores = [4, 5, 6, 7, 8, 9]
```

Yêu cầu:

```txt
vẽ scatter plot
nhận xét mối quan hệ giữa giờ học và điểm số
```

---

### Bài 4

Tạo dữ liệu điểm:

```python
scores = [5, 6, 7, 7, 8, 8, 8, 9, 10, 6, 7, 8]
```

Yêu cầu:

```txt
vẽ histogram
dùng bins=5
nhận xét dữ liệu tập trung ở khoảng nào
```

---

### Bài 5

Vẽ hàm số:

```txt
y = x^2
```

Yêu cầu:

```txt
dùng np.linspace để tạo x từ -10 đến 10
tính y = x ** 2
vẽ đồ thị bằng plt.plot
thêm grid
```

---

### Bài 6

Vẽ hai hàm số trên cùng biểu đồ:

```txt
y1 = sin(x)
y2 = cos(x)
```

Yêu cầu:

```txt
x chạy từ 0 đến 2π
thêm label cho từng đường
thêm legend
thêm grid
```

---

### Bài 7

Cho dữ liệu:

```python
epochs = [1, 2, 3, 4, 5]
train_loss = [0.9, 0.7, 0.5, 0.4, 0.3]
val_loss = [1.0, 0.8, 0.65, 0.6, 0.58]
```

Yêu cầu:

```txt
vẽ training loss và validation loss trên cùng biểu đồ
thêm marker
thêm legend
nhận xét hiện tượng overfitting nếu có
```

---

### Bài 8

Tạo DataFrame:

```python
import pandas as pd

df = pd.DataFrame({
    "name": ["An", "Binh", "Chi", "Dung"],
    "score": [8, 9, 7, 6]
})
```

Yêu cầu:

```txt
vẽ biểu đồ cột từ DataFrame
dùng plt.bar
sau đó thử dùng df.plot(kind="bar")
```

---

### Bài 9

Tạo confusion matrix:

```python
cm = np.array([
    [8, 2],
    [1, 9]
])
```

Yêu cầu:

```txt
vẽ bằng plt.imshow
thêm colorbar
thêm số vào từng ô bằng plt.text
```

---

### Bài 10

Tạo một biểu đồ bất kỳ và lưu thành file:

```txt
chart.png
```

Yêu cầu:

```txt
dùng plt.savefig("chart.png", dpi=300)
gọi savefig trước show
```

---

## 30. Tóm tắt các lệnh Matplotlib quan trọng

### Import

```python
import matplotlib.pyplot as plt
```

### Các loại biểu đồ

```python
plt.plot()
plt.bar()
plt.barh()
plt.scatter()
plt.hist()
plt.pie()
plt.boxplot()
plt.imshow()
```

### Thành phần biểu đồ

```python
plt.title()
plt.xlabel()
plt.ylabel()
plt.legend()
plt.grid()
plt.colorbar()
```

### Giới hạn trục

```python
plt.xlim()
plt.ylim()
```

### Kích thước và lưu ảnh

```python
plt.figure(figsize=(8, 5))
plt.savefig("chart.png", dpi=300)
plt.show()
```

### Subplot

```python
plt.subplot()
plt.subplots()
```

### Dùng với Figure và Axes

```python
fig, ax = plt.subplots()

ax.plot(x, y)
ax.set_title("Title")
ax.set_xlabel("x")
ax.set_ylabel("y")

plt.show()
```

---

## 31. Tóm tắt cuối

Matplotlib là thư viện Python dùng để trực quan hóa dữ liệu.

Có thể hiểu:

```txt
Matplotlib giúp biến dữ liệu thành biểu đồ.
```

Matplotlib thường được học sau NumPy và Pandas vì:

```txt
NumPy giúp tạo và xử lý dữ liệu số.
Pandas giúp đọc và xử lý dữ liệu dạng bảng.
Matplotlib giúp vẽ biểu đồ từ dữ liệu đó.
```

Các biểu đồ cơ bản cần nhớ:

```txt
Line chart      biểu đồ đường
Bar chart       biểu đồ cột
Scatter plot    biểu đồ phân tán
Histogram       biểu đồ phân phối
Pie chart       biểu đồ tròn
Boxplot         biểu đồ hộp
Heatmap/Image   biểu diễn dữ liệu dạng ma trận
```

Matplotlib rất quan trọng trong:

```txt
Data Science
Machine Learning
thống kê dữ liệu
phân tích dữ liệu
mô phỏng toán học
báo cáo dữ liệu
trực quan hóa kết quả huấn luyện mô hình
```

Phân biệt nhanh:

```txt
NumPy:
Xử lý mảng số, vector, ma trận.

Pandas:
Xử lý dữ liệu dạng bảng.

Matplotlib:
Vẽ biểu đồ.

Scikit-learn:
Xây dựng mô hình Machine Learning truyền thống.

PyTorch:
Xây dựng và huấn luyện mô hình Deep Learning.
```

Cách nhớ đơn giản:

```txt
Có dữ liệu số → dùng NumPy.
Có bảng dữ liệu → dùng Pandas.
Cần vẽ biểu đồ → dùng Matplotlib.
Cần train mô hình AI → dùng Scikit-learn hoặc PyTorch.
```
