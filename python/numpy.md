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
