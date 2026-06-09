# NumPy là gì?

## 1. Khái niệm

**NumPy** là một thư viện trong Python dùng để xử lý dữ liệu dạng mảng nhiều chiều, đặc biệt là vector và ma trận.

NumPy thường được sử dụng trong:

* Tính toán khoa học
* Xử lý dữ liệu
* Machine Learning
* Data Science
* Xử lý ảnh
* Đại số tuyến tính

Cách import NumPy thường dùng:

```python
import numpy as np
```

Trong đó `np` là tên viết tắt phổ biến của thư viện NumPy.

---

## 2. Vì sao cần NumPy?

Python có sẵn kiểu dữ liệu `list`, nhưng khi làm việc với dữ liệu số lớn, `list` không thật sự tối ưu.

NumPy giúp:

* Tính toán nhanh hơn list Python thông thường
* Làm việc dễ dàng với vector, ma trận, tensor
* Hỗ trợ nhiều phép toán toán học
* Dễ kết hợp với các thư viện Machine Learning như Pandas, Scikit-learn, TensorFlow, PyTorch
* Code ngắn gọn và rõ ràng hơn khi xử lý dữ liệu dạng số

Ví dụ:

```python
import numpy as np

arr = np.array([1, 2, 3, 4])
print(arr)
```

Kết quả:

```python
[1 2 3 4]
```

---

## 3. Mảng NumPy là gì?

Đối tượng chính trong NumPy là `ndarray`, tức là mảng nhiều chiều.

Ví dụ mảng 1 chiều:

```python
import numpy as np

arr = np.array([1, 2, 3])
print(arr)
```

Ví dụ mảng 2 chiều:

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(matrix)
```

Mảng 2 chiều có thể hiểu giống như ma trận.

---

## 4. Khác nhau giữa list Python và NumPy array

Ví dụ với list Python:

```python
a = [1, 2, 3]
b = [4, 5, 6]

print(a + b)
```

Kết quả:

```python
[1, 2, 3, 4, 5, 6]
```

Ở đây `+` dùng để nối list.

Còn với NumPy array:

```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
```

Kết quả:

```python
[5 7 9]
```

Ở đây `+` là phép cộng từng phần tử.

---

## 5. Một số thuộc tính quan trọng

```python
import numpy as np

arr = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(arr.shape)
print(arr.ndim)
print(arr.size)
print(arr.dtype)
```

Ý nghĩa:

* `shape`: kích thước của mảng
* `ndim`: số chiều của mảng
* `size`: tổng số phần tử
* `dtype`: kiểu dữ liệu của phần tử trong mảng

Ví dụ:

```python
arr.shape
```

Kết quả:

```python
(2, 3)
```

Nghĩa là mảng có 2 dòng và 3 cột.

---

## 6. Tạo mảng trong NumPy

Tạo mảng từ list:

```python
arr = np.array([1, 2, 3])
```

Tạo mảng toàn số 0:

```python
zeros = np.zeros((2, 3))
```

Tạo mảng toàn số 1:

```python
ones = np.ones((2, 3))
```

Tạo mảng gồm các số liên tiếp:

```python
arr = np.arange(1, 10)
```

Kết quả:

```python
[1 2 3 4 5 6 7 8 9]
```

Tạo mảng chia đều trong một khoảng:

```python
arr = np.linspace(0, 1, 5)
```

Kết quả:

```python
[0.   0.25 0.5  0.75 1.  ]
```

---

## 7. Phép toán với NumPy array

```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
print(a - b)
print(a * b)
print(a / b)
```

Kết quả:

```python
[5 7 9]
[-3 -3 -3]
[4 10 18]
[0.25 0.4 0.5]
```

Các phép toán này được thực hiện theo từng phần tử.

---

## 8. Truy cập phần tử

Mảng 1 chiều:

```python
arr = np.array([10, 20, 30, 40])

print(arr[0])
print(arr[2])
```

Mảng 2 chiều:

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(matrix[0, 0])
print(matrix[1, 2])
```

Ý nghĩa:

```python
matrix[1, 2]
```

Lấy phần tử ở dòng 1, cột 2.

Lưu ý: chỉ số trong Python bắt đầu từ 0.

---

## 9. Cắt mảng

```python
arr = np.array([10, 20, 30, 40, 50])

print(arr[1:4])
```

Kết quả:

```python
[20 30 40]
```

Với mảng 2 chiều:

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
])

print(matrix[0:2, 1:3])
```

Kết quả:

```python
[[2 3]
 [5 6]]
```

---

## 10. Reshape mảng

`reshape` dùng để đổi hình dạng của mảng.

```python
arr = np.array([1, 2, 3, 4, 5, 6])

matrix = arr.reshape(2, 3)

print(matrix)
```

Kết quả:

```python
[[1 2 3]
 [4 5 6]]
```

Lưu ý: số phần tử trước và sau khi reshape phải bằng nhau.

Ví dụ mảng có 6 phần tử thì có thể reshape thành:

```python
(2, 3)
(3, 2)
(1, 6)
(6, 1)
```

---

## 11. Một số hàm tính toán thường dùng

```python
arr = np.array([1, 2, 3, 4, 5])

print(np.sum(arr))
print(np.mean(arr))
print(np.max(arr))
print(np.min(arr))
print(np.std(arr))
```

Ý nghĩa:

* `np.sum`: tính tổng
* `np.mean`: tính trung bình
* `np.max`: tìm giá trị lớn nhất
* `np.min`: tìm giá trị nhỏ nhất
* `np.std`: tính độ lệch chuẩn

---

## 12. Broadcasting là gì?

Broadcasting là cơ chế cho phép NumPy thực hiện phép toán giữa các mảng có kích thước khác nhau trong một số trường hợp.

Ví dụ:

```python
arr = np.array([1, 2, 3])

print(arr + 10)
```

Kết quả:

```python
[11 12 13]
```

Ở đây số `10` được cộng vào từng phần tử của mảng.

Ví dụ khác:

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(matrix * 2)
```

Kết quả:

```python
[[ 2  4  6]
 [ 8 10 12]]
```

---

## 13. Ứng dụng của NumPy

NumPy được dùng nhiều trong Data Science và Machine Learning vì dữ liệu thường được biểu diễn dưới dạng số.

Ví dụ:

* Một ảnh màu có thể biểu diễn bằng mảng 3 chiều: chiều cao, chiều rộng, số kênh màu RGB
* Một bảng dữ liệu có thể biểu diễn bằng ma trận
* Một vector đặc trưng trong Machine Learning có thể biểu diễn bằng mảng 1 chiều
* Một batch dữ liệu có thể biểu diễn bằng tensor nhiều chiều

Ví dụ ảnh RGB:

```python
image.shape
```

Có thể cho kết quả:

```python
(256, 256, 3)
```

Nghĩa là ảnh có kích thước 256 x 256 và có 3 kênh màu: Red, Green, Blue.

---

## 14. Tóm tắt

NumPy là thư viện quan trọng trong Python để xử lý dữ liệu số.
Đối tượng chính của NumPy là `ndarray`.
NumPy giúp làm việc với vector, ma trận và tensor dễ dàng hơn.
Các phép toán trên NumPy array thường được thực hiện theo từng phần tử.
NumPy là nền tảng quan trọng cho Data Science, Machine Learning và xử lý dữ liệu.


## 15. Các lĩnh vực thường áp dụng NumPy

NumPy không chỉ dùng để tạo mảng, mà còn là nền tảng cho nhiều lĩnh vực tính toán trong Python. Khi dữ liệu được biểu diễn bằng số, vector, ma trận hoặc tensor, NumPy thường được sử dụng để xử lý.

---

### 15.1. Đại số tuyến tính

NumPy được dùng rất nhiều trong **đại số tuyến tính**, đặc biệt là khi làm việc với vector và ma trận.

Một số thao tác phổ biến:

* Cộng, trừ ma trận
* Nhân ma trận
* Tính định thức
* Tìm ma trận nghịch đảo
* Giải hệ phương trình tuyến tính
* Tính trị riêng và vector riêng

Ví dụ cộng hai ma trận:

```python
import numpy as np

A = np.array([
    [1, 2],
    [3, 4]
])

B = np.array([
    [5, 6],
    [7, 8]
])

print(A + B)
```

Kết quả:

```python
[[ 6  8]
 [10 12]]
```

Ví dụ nhân ma trận:

```python
C = np.dot(A, B)
print(C)
```

Hoặc dùng toán tử `@`:

```python
C = A @ B
print(C)
```

Ví dụ tính định thức:

```python
det_A = np.linalg.det(A)
print(det_A)
```

Ví dụ tìm ma trận nghịch đảo:

```python
inv_A = np.linalg.inv(A)
print(inv_A)
```

Ví dụ giải hệ phương trình tuyến tính:

Giả sử có hệ:

```txt
x + 2y = 5
3x + 4y = 11
```

Ta viết dưới dạng ma trận:

```python
A = np.array([
    [1, 2],
    [3, 4]
])

b = np.array([5, 11])

x = np.linalg.solve(A, b)
print(x)
```

Kết quả:

```python
[1. 2.]
```

Nghĩa là:

```txt
x = 1, y = 2
```

---

### 15.2. Thống kê và xử lý dữ liệu

NumPy thường được dùng để tính toán thống kê cơ bản trên dữ liệu.

Một số hàm thường dùng:

```python
np.sum()
np.mean()
np.median()
np.max()
np.min()
np.std()
np.var()
```

Ví dụ:

```python
scores = np.array([7, 8, 9, 6, 10])

print(np.mean(scores))
print(np.max(scores))
print(np.min(scores))
print(np.std(scores))
```

Ý nghĩa:

* `mean`: giá trị trung bình
* `max`: giá trị lớn nhất
* `min`: giá trị nhỏ nhất
* `std`: độ lệch chuẩn

NumPy thường được dùng trước khi đưa dữ liệu vào các thư viện như Pandas, Scikit-learn hoặc PyTorch.

---

### 15.3. Machine Learning

Trong Machine Learning, dữ liệu thường được biểu diễn dưới dạng vector, ma trận hoặc tensor.

Ví dụ:

* Một dòng dữ liệu là một vector đặc trưng
* Một bảng dữ liệu là một ma trận
* Nhiều ảnh hoặc nhiều mẫu dữ liệu có thể biểu diễn bằng tensor nhiều chiều

Ví dụ một mẫu dữ liệu có 4 đặc trưng:

```python
x = np.array([1.75, 70, 23, 1])
```

Có thể hiểu là:

```txt
chiều cao = 1.75
cân nặng = 70
tuổi = 23
giới tính = 1
```

Một tập dữ liệu gồm nhiều mẫu:

```python
X = np.array([
    [1.75, 70, 23, 1],
    [1.60, 50, 21, 0],
    [1.80, 80, 25, 1]
])
```

Ở đây:

```python
X.shape
```

Kết quả:

```python
(3, 4)
```

Nghĩa là có 3 mẫu dữ liệu, mỗi mẫu có 4 đặc trưng.

Trong Machine Learning, NumPy thường dùng để:

* Biểu diễn dữ liệu đầu vào
* Chuẩn hóa dữ liệu
* Tính toán vector và ma trận
* Viết thử các thuật toán học máy cơ bản
* Xử lý dữ liệu trước khi đưa vào mô hình

---

### 15.4. Deep Learning

Trong Deep Learning, dữ liệu thường được biểu diễn dưới dạng tensor nhiều chiều.

Ví dụ một ảnh màu RGB có thể có dạng:

```python
image = np.zeros((224, 224, 3))
```

Ý nghĩa:

```txt
224: chiều cao ảnh
224: chiều rộng ảnh
3: số kênh màu RGB
```

Nếu có nhiều ảnh trong một batch:

```python
batch_images = np.zeros((32, 224, 224, 3))
```

Ý nghĩa:

```txt
32: số ảnh trong batch
224: chiều cao
224: chiều rộng
3: số kênh màu
```

NumPy giúp ta hiểu cách dữ liệu được tổ chức trước khi học các thư viện như TensorFlow hoặc PyTorch.

---

### 15.5. Xử lý ảnh

Một ảnh có thể được biểu diễn bằng mảng số.

Ví dụ ảnh xám:

```python
gray_image = np.array([
    [0, 255, 100],
    [50, 200, 150],
    [30, 80, 220]
])
```

Mỗi số biểu diễn độ sáng của một pixel.

Với ảnh RGB, mỗi pixel có 3 giá trị màu:

```txt
Red, Green, Blue
```

Ví dụ:

```python
pixel = np.array([255, 0, 0])
```

Đây là màu đỏ.

NumPy có thể được dùng để:

* Thay đổi độ sáng ảnh
* Cắt ảnh
* Lật ảnh
* Chuẩn hóa pixel
* Biểu diễn ảnh dưới dạng ma trận

Ví dụ tăng độ sáng:

```python
image = np.array([
    [100, 120],
    [130, 140]
])

bright_image = image + 30
print(bright_image)
```

---

### 15.6. Xử lý tín hiệu

NumPy cũng được dùng trong xử lý tín hiệu, ví dụ:

* Âm thanh
* Sóng
* Dữ liệu cảm biến
* Tín hiệu điện
* Tín hiệu IoT

Một đoạn tín hiệu âm thanh có thể được biểu diễn bằng mảng 1 chiều:

```python
signal = np.array([0.1, 0.2, 0.4, 0.3, 0.1])
```

Mỗi phần tử có thể biểu diễn biên độ âm thanh tại một thời điểm.

NumPy có thể dùng để:

* Tính trung bình tín hiệu
* Chuẩn hóa tín hiệu
* Cắt một đoạn tín hiệu
* Biến đổi dữ liệu tín hiệu thành dạng phù hợp để phân tích

---

### 15.7. Mô phỏng toán học và khoa học

NumPy thường được dùng để mô phỏng các bài toán toán học, vật lý hoặc khoa học.

Ví dụ tạo dãy giá trị của hàm số:

```python
x = np.linspace(-10, 10, 100)
y = x ** 2
```

Ở đây:

```python
x
```

là 100 giá trị từ -10 đến 10.

```python
y
```

là giá trị tương ứng của hàm:

```txt
y = x^2
```

Dữ liệu này có thể dùng để vẽ đồ thị bằng Matplotlib.

Ví dụ:

```python
import matplotlib.pyplot as plt

plt.plot(x, y)
plt.show()
```

---

### 15.8. Data Science

Trong Data Science, NumPy thường nằm ở tầng nền tảng.

Các thư viện như:

```txt
Pandas
Scikit-learn
Matplotlib
TensorFlow
PyTorch
```

đều có liên hệ chặt chẽ với NumPy.

NumPy thường được dùng để:

* Tạo dữ liệu mẫu
* Làm sạch dữ liệu dạng số
* Tính toán thống kê
* Biến đổi dữ liệu
* Chuẩn hóa dữ liệu
* Làm việc với vector, ma trận

Ví dụ chuẩn hóa dữ liệu:

```python
data = np.array([10, 20, 30, 40, 50])

normalized = (data - np.mean(data)) / np.std(data)

print(normalized)
```

Chuẩn hóa giúp dữ liệu có trung bình gần 0 và độ lệch chuẩn gần 1.

---

## 16. Tóm tắt các ứng dụng chính của NumPy

NumPy được áp dụng trong nhiều lĩnh vực vì nó xử lý dữ liệu số rất tốt.

Các ứng dụng quan trọng:

```txt
1. Đại số tuyến tính
2. Thống kê
3. Xử lý dữ liệu
4. Machine Learning
5. Deep Learning
6. Xử lý ảnh
7. Xử lý tín hiệu
8. Mô phỏng toán học
9. Data Science
```

Có thể hiểu đơn giản:

```txt
Nếu dữ liệu có thể biểu diễn bằng số, vector, ma trận hoặc tensor,
thì NumPy có thể được dùng để xử lý dữ liệu đó.
```

NumPy là một thư viện nền tảng. Khi học tốt NumPy, việc học Pandas, Machine Learning, Deep Learning, xử lý ảnh và xử lý dữ liệu sẽ dễ hiểu hơn rất nhiều.

Một số lệnh cần nhớ:

```python
import numpy as np

np.array()
np.zeros()
np.ones()
np.arange()
np.linspace()
arr.shape
arr.ndim
arr.size
arr.dtype
arr.reshape()
np.sum()
np.mean()
np.max()
np.min()
```