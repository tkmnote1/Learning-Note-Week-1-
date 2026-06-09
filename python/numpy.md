# NumPy trong Python

## 1. NumPy là gì?

**NumPy** là viết tắt của **Numerical Python**.

NumPy là thư viện Python dùng để làm việc với dữ liệu số, đặc biệt là:

```txt
mảng một chiều
mảng nhiều chiều
vector
ma trận
tensor
đại số tuyến tính
thống kê
tính toán khoa học
```

Cách import NumPy thường dùng:

```python
import numpy as np
```

Trong đó `np` là bí danh phổ biến của NumPy.

Ví dụ đầu tiên:

```python
import numpy as np

arr = np.array([1, 2, 3, 4])

print(arr)
```

Kết quả:

```txt
[1 2 3 4]
```

---

## 2. Vì sao cần NumPy?

Python có sẵn kiểu dữ liệu `list`, nhưng khi làm việc với dữ liệu số lớn, `list` có một số hạn chế:

```txt
tính toán chậm hơn
không tối ưu cho dữ liệu nhiều chiều
không hỗ trợ tốt phép toán vector và ma trận
code dài hơn khi xử lý dữ liệu số
```

NumPy giúp:

```txt
xử lý dữ liệu số nhanh hơn
làm việc tốt với vector, ma trận, tensor
hỗ trợ nhiều hàm toán học
hỗ trợ đại số tuyến tính
hỗ trợ thống kê
hỗ trợ broadcasting
là nền tảng cho nhiều thư viện Data Science và Machine Learning
```

Các thư viện thường dùng NumPy hoặc có liên hệ chặt chẽ với NumPy:

```txt
Pandas
Matplotlib
Scikit-learn
TensorFlow
PyTorch
OpenCV
SciPy
```

Có thể hiểu đơn giản:

```txt
NumPy là nền tảng xử lý dữ liệu số trong Python.
```

---

## 3. NumPy array là gì?

Đối tượng quan trọng nhất trong NumPy là:

```txt
ndarray
```

`ndarray` nghĩa là **N-dimensional array**, tức là mảng N chiều.

Ví dụ mảng 1 chiều:

```python
import numpy as np

arr = np.array([1, 2, 3])

print(arr)
```

Kết quả:

```txt
[1 2 3]
```

Ví dụ mảng 2 chiều:

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(matrix)
```

Kết quả:

```txt
[[1 2 3]
 [4 5 6]]
```

Ví dụ mảng 3 chiều:

```python
tensor = np.array([
    [
        [1, 2],
        [3, 4]
    ],
    [
        [5, 6],
        [7, 8]
    ]
])

print(tensor)
```

Mảng 3 chiều thường gặp khi làm việc với ảnh, video, hoặc dữ liệu Deep Learning.

---

## 4. Sự khác nhau giữa Python list và NumPy array

### 4.1. List Python

```python
a = [1, 2, 3]
b = [4, 5, 6]

print(a + b)
```

Kết quả:

```txt
[1, 2, 3, 4, 5, 6]
```

Trong list Python, toán tử `+` dùng để nối list.

---

### 4.2. NumPy array

```python
import numpy as np

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
```

Kết quả:

```txt
[5 7 9]
```

Trong NumPy array, toán tử `+` thực hiện cộng từng phần tử.

---

## 5. Vì sao NumPy nhanh hơn list Python?

NumPy nhanh hơn vì:

```txt
dữ liệu trong NumPy array thường cùng một kiểu
dữ liệu được lưu liên tục trong bộ nhớ
nhiều phép toán được cài đặt bằng C ở bên dưới
NumPy hỗ trợ vectorization
```

Ví dụ với list Python:

```python
a = [1, 2, 3, 4]
b = []

for x in a:
    b.append(x * 2)

print(b)
```

Với NumPy:

```python
import numpy as np

a = np.array([1, 2, 3, 4])

b = a * 2

print(b)
```

Kết quả:

```txt
[2 4 6 8]
```

NumPy giúp code ngắn hơn và chạy nhanh hơn.

---

## 6. Vectorization là gì?

**Vectorization** là cách thực hiện phép toán trên toàn bộ mảng mà không cần viết vòng lặp thủ công.

Ví dụ không dùng vectorization:

```python
arr = [1, 2, 3, 4]
result = []

for x in arr:
    result.append(x * 2)

print(result)
```

Dùng NumPy vectorization:

```python
import numpy as np

arr = np.array([1, 2, 3, 4])
result = arr * 2

print(result)
```

Kết quả:

```txt
[2 4 6 8]
```

Có thể hiểu:

```txt
Thay vì xử lý từng phần tử bằng vòng lặp Python,
NumPy xử lý cả mảng bằng phép toán vector hóa.
```

---

## 7. Tạo NumPy array

### 7.1. Tạo array từ list

```python
import numpy as np

arr = np.array([1, 2, 3, 4])

print(arr)
```

---

### 7.2. Tạo ma trận từ list lồng nhau

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(matrix)
```

---

### 7.3. Tạo array toàn số 0

```python
zeros = np.zeros(5)

print(zeros)
```

Kết quả:

```txt
[0. 0. 0. 0. 0.]
```

Tạo ma trận toàn số 0:

```python
zeros_matrix = np.zeros((2, 3))

print(zeros_matrix)
```

Kết quả:

```txt
[[0. 0. 0.]
 [0. 0. 0.]]
```

---

### 7.4. Tạo array toàn số 1

```python
ones = np.ones(5)

print(ones)
```

Tạo ma trận toàn số 1:

```python
ones_matrix = np.ones((2, 3))

print(ones_matrix)
```

---

### 7.5. Tạo array với một giá trị cố định

```python
arr = np.full((2, 3), 7)

print(arr)
```

Kết quả:

```txt
[[7 7 7]
 [7 7 7]]
```

---

### 7.6. Tạo ma trận đơn vị

```python
identity = np.eye(3)

print(identity)
```

Kết quả:

```txt
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]]
```

Ma trận đơn vị thường dùng trong đại số tuyến tính.

---

### 7.7. Tạo array bằng `arange`

```python
arr = np.arange(1, 10)

print(arr)
```

Kết quả:

```txt
[1 2 3 4 5 6 7 8 9]
```

Có bước nhảy:

```python
arr = np.arange(0, 10, 2)

print(arr)
```

Kết quả:

```txt
[0 2 4 6 8]
```

---

### 7.8. Tạo array bằng `linspace`

`linspace` dùng để tạo các giá trị cách đều nhau trong một khoảng.

```python
arr = np.linspace(0, 1, 5)

print(arr)
```

Kết quả:

```txt
[0.   0.25 0.5  0.75 1.  ]
```

Ý nghĩa:

```txt
Tạo 5 giá trị cách đều từ 0 đến 1.
```

---

### 7.9. Tạo array ngẫu nhiên

```python
random_arr = np.random.rand(5)

print(random_arr)
```

Tạo ma trận ngẫu nhiên kích thước 2 x 3:

```python
random_matrix = np.random.rand(2, 3)

print(random_matrix)
```

Tạo số nguyên ngẫu nhiên:

```python
arr = np.random.randint(1, 10, size=5)

print(arr)
```

Tạo ma trận số nguyên ngẫu nhiên:

```python
matrix = np.random.randint(1, 10, size=(2, 3))

print(matrix)
```

---

## 8. Các thuộc tính quan trọng của NumPy array

Ví dụ:

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

```txt
shape: kích thước của mảng
ndim: số chiều của mảng
size: tổng số phần tử
dtype: kiểu dữ liệu của phần tử
```

Kết quả:

```txt
(2, 3)
2
6
int64
```

Giải thích:

```txt
arr.shape = (2, 3) nghĩa là mảng có 2 dòng, 3 cột
arr.ndim = 2 nghĩa là mảng 2 chiều
arr.size = 6 nghĩa là có tổng cộng 6 phần tử
arr.dtype = int64 nghĩa là phần tử có kiểu số nguyên 64-bit
```

---

## 9. Kiểu dữ liệu trong NumPy

NumPy array thường chứa các phần tử cùng kiểu dữ liệu.

Một số kiểu dữ liệu thường gặp:

```txt
int32
int64
float32
float64
bool
str
```

Ví dụ:

```python
arr = np.array([1, 2, 3], dtype=np.float64)

print(arr)
print(arr.dtype)
```

Kết quả:

```txt
[1. 2. 3.]
float64
```

Chuyển kiểu dữ liệu:

```python
arr = np.array([1.2, 2.5, 3.8])

new_arr = arr.astype(int)

print(new_arr)
```

Kết quả:

```txt
[1 2 3]
```

---

## 10. Truy cập phần tử trong NumPy array

### 10.1. Mảng 1 chiều

```python
arr = np.array([10, 20, 30, 40])

print(arr[0])
print(arr[1])
print(arr[-1])
```

Kết quả:

```txt
10
20
40
```

Lưu ý:

```txt
Chỉ số trong Python bắt đầu từ 0.
arr[-1] là phần tử cuối cùng.
```

---

### 10.2. Mảng 2 chiều

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(matrix[0, 0])
print(matrix[0, 2])
print(matrix[1, 1])
```

Kết quả:

```txt
1
3
5
```

Ý nghĩa:

```txt
matrix[row, column]
```

Ví dụ:

```python
matrix[1, 1]
```

là phần tử ở dòng 1, cột 1.

---

## 11. Cắt mảng với slicing

### 11.1. Slicing mảng 1 chiều

```python
arr = np.array([10, 20, 30, 40, 50])

print(arr[1:4])
```

Kết quả:

```txt
[20 30 40]
```

Ý nghĩa:

```txt
arr[start:end]
lấy từ start đến trước end
```

Ví dụ:

```python
print(arr[:3])
print(arr[2:])
print(arr[::2])
```

Kết quả:

```txt
[10 20 30]
[30 40 50]
[10 30 50]
```

---

### 11.2. Slicing mảng 2 chiều

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
])

print(matrix[0:2, 1:3])
```

Kết quả:

```txt
[[2 3]
 [5 6]]
```

Ý nghĩa:

```txt
matrix[0:2, 1:3]
lấy dòng 0 đến trước dòng 2
lấy cột 1 đến trước cột 3
```

Lấy một cột:

```python
print(matrix[:, 0])
```

Kết quả:

```txt
[1 4 7]
```

Lấy một dòng:

```python
print(matrix[1, :])
```

Kết quả:

```txt
[4 5 6]
```

---

## 12. Thay đổi giá trị phần tử

```python
arr = np.array([10, 20, 30])

arr[0] = 100

print(arr)
```

Kết quả:

```txt
[100  20  30]
```

Với mảng 2 chiều:

```python
matrix = np.array([
    [1, 2],
    [3, 4]
])

matrix[0, 1] = 99

print(matrix)
```

Kết quả:

```txt
[[ 1 99]
 [ 3  4]]
```

---

## 13. Reshape mảng

`reshape` dùng để đổi hình dạng của mảng.

```python
arr = np.array([1, 2, 3, 4, 5, 6])

matrix = arr.reshape(2, 3)

print(matrix)
```

Kết quả:

```txt
[[1 2 3]
 [4 5 6]]
```

Có thể reshape mảng 6 phần tử thành:

```txt
(2, 3)
(3, 2)
(1, 6)
(6, 1)
```

Không thể reshape thành kích thước có số phần tử khác.

Ví dụ sai:

```python
arr.reshape(4, 4)
```

Vì mảng có 6 phần tử, không thể đổi thành 16 phần tử.

---

## 14. Flatten và ravel

Dùng để chuyển mảng nhiều chiều thành mảng 1 chiều.

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

flat = matrix.flatten()

print(flat)
```

Kết quả:

```txt
[1 2 3 4 5 6]
```

Dùng `ravel`:

```python
flat = matrix.ravel()

print(flat)
```

Khác nhau cơ bản:

```txt
flatten thường tạo bản sao mới
ravel thường trả về view nếu có thể
```

---

## 15. Phép toán cơ bản với NumPy array

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
print(a - b)
print(a * b)
print(a / b)
```

Kết quả:

```txt
[5 7 9]
[-3 -3 -3]
[ 4 10 18]
[0.25 0.4  0.5 ]
```

Các phép toán này thực hiện theo từng phần tử.

---

## 16. Phép toán với số

```python
arr = np.array([1, 2, 3])

print(arr + 10)
print(arr - 10)
print(arr * 10)
print(arr / 10)
print(arr ** 2)
```

Kết quả:

```txt
[11 12 13]
[-9 -8 -7]
[10 20 30]
[0.1 0.2 0.3]
[1 4 9]
```

---

## 17. Các hàm toán học thường dùng

```python
arr = np.array([1, 4, 9, 16])

print(np.sqrt(arr))
print(np.exp(arr))
print(np.log(arr))
```

Ý nghĩa:

```txt
np.sqrt: căn bậc hai
np.exp: hàm mũ e^x
np.log: log tự nhiên
```

Ví dụ lượng giác:

```python
angles = np.array([0, np.pi / 2, np.pi])

print(np.sin(angles))
print(np.cos(angles))
```

---

## 18. Hàm thống kê cơ bản

```python
arr = np.array([1, 2, 3, 4, 5])

print(np.sum(arr))
print(np.mean(arr))
print(np.median(arr))
print(np.max(arr))
print(np.min(arr))
print(np.std(arr))
print(np.var(arr))
```

Ý nghĩa:

```txt
sum: tổng
mean: trung bình
median: trung vị
max: giá trị lớn nhất
min: giá trị nhỏ nhất
std: độ lệch chuẩn
var: phương sai
```

Kết quả:

```txt
15
3.0
3.0
5
1
1.4142135623730951
2.0
```

---

## 19. Tính theo trục với axis

Trong NumPy, `axis` rất quan trọng.

Với ma trận 2 chiều:

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])
```

Tổng toàn bộ:

```python
print(np.sum(matrix))
```

Kết quả:

```txt
21
```

Tổng theo cột:

```python
print(np.sum(matrix, axis=0))
```

Kết quả:

```txt
[5 7 9]
```

Tổng theo dòng:

```python
print(np.sum(matrix, axis=1))
```

Kết quả:

```txt
[ 6 15]
```

Cách nhớ:

```txt
axis=0: tính theo chiều dọc, gom các dòng lại, kết quả theo cột
axis=1: tính theo chiều ngang, gom các cột lại, kết quả theo dòng
```

Ví dụ trung bình theo cột:

```python
print(np.mean(matrix, axis=0))
```

Ví dụ trung bình theo dòng:

```python
print(np.mean(matrix, axis=1))
```

---

## 20. Broadcasting là gì?

**Broadcasting** là cơ chế cho phép NumPy thực hiện phép toán giữa các array có shape khác nhau, miễn là chúng tương thích.

Ví dụ đơn giản:

```python
arr = np.array([1, 2, 3])

print(arr + 10)
```

Kết quả:

```txt
[11 12 13]
```

Số `10` được tự động mở rộng để cộng với từng phần tử.

Ví dụ với ma trận:

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

row = np.array([10, 20, 30])

print(matrix + row)
```

Kết quả:

```txt
[[11 22 33]
 [14 25 36]]
```

Ở đây `row` được cộng vào từng dòng của `matrix`.

---

## 21. Điều kiện và lọc dữ liệu

NumPy cho phép lọc dữ liệu bằng điều kiện.

```python
arr = np.array([1, 2, 3, 4, 5, 6])

print(arr > 3)
```

Kết quả:

```txt
[False False False  True  True  True]
```

Lọc các phần tử lớn hơn 3:

```python
result = arr[arr > 3]

print(result)
```

Kết quả:

```txt
[4 5 6]
```

Lọc số chẵn:

```python
even_numbers = arr[arr % 2 == 0]

print(even_numbers)
```

Kết quả:

```txt
[2 4 6]
```

---

## 22. Kết hợp nhiều điều kiện

```python
arr = np.array([1, 2, 3, 4, 5, 6, 7, 8])

result = arr[(arr > 3) & (arr < 8)]

print(result)
```

Kết quả:

```txt
[4 5 6 7]
```

Lưu ý:

```txt
Trong NumPy:
& là AND
| là OR
~ là NOT
```

Phải đặt từng điều kiện trong dấu ngoặc:

```python
(arr > 3) & (arr < 8)
```

Không nên viết:

```python
arr > 3 & arr < 8
```

vì dễ sai thứ tự ưu tiên toán tử.

---

## 23. `np.where`

`np.where` dùng để chọn giá trị theo điều kiện.

Ví dụ:

```python
arr = np.array([1, 2, 3, 4, 5])

result = np.where(arr >= 3, "big", "small")

print(result)
```

Kết quả:

```txt
['small' 'small' 'big' 'big' 'big']
```

Ý nghĩa:

```txt
Nếu arr >= 3 thì lấy "big"
Ngược lại lấy "small"
```

Ví dụ thay số âm bằng 0:

```python
arr = np.array([-2, -1, 0, 1, 2])

result = np.where(arr < 0, 0, arr)

print(result)
```

Kết quả:

```txt
[0 0 0 1 2]
```

---

## 24. Sắp xếp array

```python
arr = np.array([5, 2, 9, 1, 7])

sorted_arr = np.sort(arr)

print(sorted_arr)
```

Kết quả:

```txt
[1 2 5 7 9]
```

Với ma trận:

```python
matrix = np.array([
    [3, 1, 2],
    [9, 7, 8]
])

print(np.sort(matrix, axis=1))
```

Kết quả:

```txt
[[1 2 3]
 [7 8 9]]
```

Sắp xếp từng dòng.

---

## 25. Nối array

### 25.1. `np.concatenate`

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

c = np.concatenate([a, b])

print(c)
```

Kết quả:

```txt
[1 2 3 4 5 6]
```

---

### 25.2. Nối ma trận theo dòng và cột

```python
A = np.array([
    [1, 2],
    [3, 4]
])

B = np.array([
    [5, 6],
    [7, 8]
])
```

Nối theo dòng:

```python
result = np.concatenate([A, B], axis=0)

print(result)
```

Kết quả:

```txt
[[1 2]
 [3 4]
 [5 6]
 [7 8]]
```

Nối theo cột:

```python
result = np.concatenate([A, B], axis=1)

print(result)
```

Kết quả:

```txt
[[1 2 5 6]
 [3 4 7 8]]
```

---

## 26. `vstack` và `hstack`

Nối theo chiều dọc:

```python
result = np.vstack([A, B])

print(result)
```

Nối theo chiều ngang:

```python
result = np.hstack([A, B])

print(result)
```

Cách nhớ:

```txt
vstack: vertical stack, nối dọc
hstack: horizontal stack, nối ngang
```

---

## 27. Tách array

```python
arr = np.array([1, 2, 3, 4, 5, 6])

result = np.split(arr, 3)

print(result)
```

Kết quả:

```txt
[array([1, 2]), array([3, 4]), array([5, 6])]
```

Với ma trận:

```python
matrix = np.array([
    [1, 2, 3, 4],
    [5, 6, 7, 8]
])

left, right = np.hsplit(matrix, 2)

print(left)
print(right)
```

---

## 28. Copy và view

Trong NumPy, cần phân biệt:

```txt
copy: bản sao độc lập
view: nhìn vào cùng vùng dữ liệu gốc
```

Ví dụ view:

```python
arr = np.array([1, 2, 3])

view_arr = arr.view()

view_arr[0] = 100

print(arr)
print(view_arr)
```

Kết quả:

```txt
[100   2   3]
[100   2   3]
```

Vì `view_arr` và `arr` chia sẻ dữ liệu.

Ví dụ copy:

```python
arr = np.array([1, 2, 3])

copy_arr = arr.copy()

copy_arr[0] = 100

print(arr)
print(copy_arr)
```

Kết quả:

```txt
[1 2 3]
[100   2   3]
```

Cách nhớ:

```txt
copy: sửa bản sao không ảnh hưởng bản gốc
view: sửa view có thể ảnh hưởng bản gốc
```

---

## 29. Đại số tuyến tính với NumPy

NumPy hỗ trợ mạnh các phép toán đại số tuyến tính thông qua module:

```python
np.linalg
```

---

### 29.1. Vector

```python
v = np.array([1, 2, 3])

print(v)
```

Vector có thể dùng để biểu diễn:

```txt
điểm trong không gian
đặc trưng dữ liệu
vector trọng số trong Machine Learning
```

---

### 29.2. Ma trận

```python
A = np.array([
    [1, 2],
    [3, 4]
])

print(A)
```

---

### 29.3. Cộng và trừ ma trận

```python
A = np.array([
    [1, 2],
    [3, 4]
])

B = np.array([
    [5, 6],
    [7, 8]
])

print(A + B)
print(A - B)
```

---

### 29.4. Nhân từng phần tử

```python
print(A * B)
```

Kết quả:

```txt
[[ 5 12]
 [21 32]]
```

Lưu ý:

```txt
A * B trong NumPy là nhân từng phần tử, không phải nhân ma trận.
```

---

### 29.5. Nhân ma trận

Dùng toán tử `@`:

```python
C = A @ B

print(C)
```

Hoặc:

```python
C = np.matmul(A, B)

print(C)
```

Hoặc:

```python
C = np.dot(A, B)

print(C)
```

Với ma trận, nên dùng:

```python
A @ B
```

cho dễ đọc.

---

### 29.6. Chuyển vị ma trận

```python
A = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(A.T)
```

Kết quả:

```txt
[[1 4]
 [2 5]
 [3 6]]
```

---

### 29.7. Định thức

```python
A = np.array([
    [1, 2],
    [3, 4]
])

det_A = np.linalg.det(A)

print(det_A)
```

Kết quả gần đúng:

```txt
-2.0000000000000004
```

Lưu ý: do sai số số thực, kết quả có thể không đúng tuyệt đối như toán tay.

---

### 29.8. Ma trận nghịch đảo

```python
inv_A = np.linalg.inv(A)

print(inv_A)
```

Chỉ ma trận vuông và khả nghịch mới có nghịch đảo.

Nếu ma trận không khả nghịch, NumPy sẽ báo lỗi.

---

### 29.9. Giải hệ phương trình tuyến tính

Giả sử có hệ:

```txt
x + 2y = 5
3x + 4y = 11
```

Viết dưới dạng:

```txt
A x = b
```

Code:

```python
A = np.array([
    [1, 2],
    [3, 4]
])

b = np.array([5, 11])

solution = np.linalg.solve(A, b)

print(solution)
```

Kết quả:

```txt
[1. 2.]
```

Nghĩa là:

```txt
x = 1
y = 2
```

---

### 29.10. Trị riêng và vector riêng

```python
A = np.array([
    [2, 0],
    [0, 3]
])

eigenvalues, eigenvectors = np.linalg.eig(A)

print(eigenvalues)
print(eigenvectors)
```

Kết quả:

```txt
[2. 3.]
[[1. 0.]
 [0. 1.]]
```

Trị riêng và vector riêng thường dùng trong:

```txt
đại số tuyến tính
PCA
Machine Learning
phân tích dữ liệu
đồ họa máy tính
```

---

## 30. Tích vô hướng và chuẩn vector

### 30.1. Tích vô hướng

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

dot_product = np.dot(a, b)

print(dot_product)
```

Kết quả:

```txt
32
```

Vì:

```txt
1*4 + 2*5 + 3*6 = 32
```

---

### 30.2. Chuẩn vector

```python
v = np.array([3, 4])

norm_v = np.linalg.norm(v)

print(norm_v)
```

Kết quả:

```txt
5.0
```

Vì:

```txt
sqrt(3^2 + 4^2) = 5
```

---

## 31. NumPy trong thống kê

NumPy có thể dùng để phân tích dữ liệu số đơn giản.

```python
data = np.array([10, 20, 30, 40, 50])

print(np.mean(data))
print(np.median(data))
print(np.var(data))
print(np.std(data))
```

Ý nghĩa:

```txt
mean: trung bình
median: trung vị
var: phương sai
std: độ lệch chuẩn
```

Ví dụ chuẩn hóa dữ liệu:

```python
data = np.array([10, 20, 30, 40, 50])

normalized = (data - np.mean(data)) / np.std(data)

print(normalized)
```

Chuẩn hóa giúp dữ liệu có trung bình gần 0 và độ lệch chuẩn gần 1.

---

## 32. NumPy trong Data Science

Trong Data Science, dữ liệu thường được biểu diễn dưới dạng bảng hoặc ma trận.

Ví dụ một dataset có 3 mẫu, mỗi mẫu có 4 đặc trưng:

```python
X = np.array([
    [1.75, 70, 23, 1],
    [1.60, 50, 21, 0],
    [1.80, 80, 25, 1]
])

print(X.shape)
```

Kết quả:

```txt
(3, 4)
```

Ý nghĩa:

```txt
3 mẫu dữ liệu
4 đặc trưng cho mỗi mẫu
```

Ví dụ một vector nhãn:

```python
y = np.array([1, 0, 1])
```

Có thể hiểu:

```txt
X là dữ liệu đầu vào
y là nhãn hoặc kết quả cần dự đoán
```

---

## 33. NumPy trong Machine Learning

Trong Machine Learning, NumPy thường dùng để:

```txt
biểu diễn dữ liệu đầu vào
biểu diễn trọng số
tính toán vector
tính toán ma trận
chuẩn hóa dữ liệu
viết thuật toán học máy cơ bản
```

Ví dụ mô hình tuyến tính đơn giản:

```python
X = np.array([
    [1, 2],
    [3, 4],
    [5, 6]
])

w = np.array([0.5, 0.2])

y_pred = X @ w

print(y_pred)
```

Kết quả:

```txt
[0.9 2.3 3.7]
```

Ở đây:

```txt
X là ma trận dữ liệu
w là vector trọng số
X @ w là phép nhân ma trận-vector
```

---

## 34. NumPy trong Deep Learning

Trong Deep Learning, dữ liệu thường được biểu diễn bằng tensor nhiều chiều.

Ví dụ một ảnh RGB:

```python
image = np.zeros((224, 224, 3))
```

Ý nghĩa:

```txt
224: chiều cao
224: chiều rộng
3: ba kênh màu RGB
```

Ví dụ một batch gồm 32 ảnh:

```python
batch_images = np.zeros((32, 224, 224, 3))
```

Ý nghĩa:

```txt
32: số ảnh trong batch
224: chiều cao ảnh
224: chiều rộng ảnh
3: số kênh màu RGB
```

NumPy giúp hiểu cách dữ liệu được tổ chức trước khi học PyTorch hoặc TensorFlow.

---

## 35. NumPy trong xử lý ảnh

Một ảnh có thể được biểu diễn bằng mảng số.

Ảnh xám:

```python
gray_image = np.array([
    [0, 255, 100],
    [50, 200, 150],
    [30, 80, 220]
])
```

Mỗi số biểu diễn độ sáng của một pixel.

Ảnh RGB:

```python
pixel = np.array([255, 0, 0])
```

Ý nghĩa:

```txt
Red = 255
Green = 0
Blue = 0
```

Đây là màu đỏ.

Ví dụ tăng độ sáng ảnh xám:

```python
image = np.array([
    [100, 120],
    [130, 140]
])

bright_image = image + 30

print(bright_image)
```

Kết quả:

```txt
[[130 150]
 [160 170]]
```

Trong thực tế cần chú ý giá trị pixel thường nằm trong khoảng:

```txt
0 đến 255
```

---

## 36. NumPy trong xử lý tín hiệu

Tín hiệu âm thanh, cảm biến hoặc IoT có thể được biểu diễn bằng mảng 1 chiều.

Ví dụ:

```python
signal = np.array([0.1, 0.2, 0.4, 0.3, 0.1])
```

Mỗi phần tử có thể biểu diễn biên độ tín hiệu tại một thời điểm.

Có thể xử lý tín hiệu bằng NumPy:

```python
print(np.mean(signal))
print(np.max(signal))
print(np.min(signal))
```

Ứng dụng:

```txt
xử lý âm thanh
dữ liệu cảm biến
dữ liệu IoT
lọc tín hiệu
phân tích chuỗi thời gian
```

---

## 37. NumPy trong mô phỏng toán học

NumPy thường dùng để tạo dữ liệu cho hàm số và mô phỏng toán học.

Ví dụ vẽ hàm:

```txt
y = x^2
```

Tạo dữ liệu:

```python
import numpy as np

x = np.linspace(-10, 10, 100)
y = x ** 2

print(x)
print(y)
```

Sau đó có thể dùng Matplotlib để vẽ:

```python
import matplotlib.pyplot as plt

plt.plot(x, y)
plt.show()
```

---

## 38. NumPy và Matplotlib

NumPy thường tạo dữ liệu số, Matplotlib dùng để vẽ dữ liệu đó.

Ví dụ:

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0, 2 * np.pi, 100)
y = np.sin(x)

plt.plot(x, y)

plt.title("Sine Function")
plt.xlabel("x")
plt.ylabel("sin(x)")

plt.show()
```

Quy trình:

```txt
NumPy tạo dữ liệu
Matplotlib vẽ biểu đồ
```

---

## 39. NumPy và Pandas

Pandas thường dùng để xử lý bảng dữ liệu, còn NumPy xử lý mảng số.

Ví dụ chuyển DataFrame sang NumPy array:

```python
import pandas as pd
import numpy as np

df = pd.DataFrame({
    "age": [20, 21, 22],
    "score": [8.5, 9.0, 7.5]
})

arr = df.to_numpy()

print(arr)
```

Kết quả:

```txt
[[20.   8.5]
 [21.   9. ]
 [22.   7.5]]
```

Có thể hiểu:

```txt
Pandas mạnh về bảng dữ liệu có tên cột
NumPy mạnh về tính toán số trên mảng
```

---

## 40. NumPy và PyTorch

NumPy dùng `ndarray`.

PyTorch dùng `Tensor`.

Điểm giống:

```txt
đều xử lý dữ liệu dạng mảng nhiều chiều
đều hỗ trợ phép toán vector, ma trận
cú pháp nhiều chỗ khá giống nhau
```

Điểm khác:

```txt
NumPy chủ yếu dùng cho tính toán số trên CPU
PyTorch dùng nhiều cho Machine Learning và Deep Learning
PyTorch hỗ trợ GPU tốt hơn
PyTorch có autograd để tự động tính đạo hàm
```

Chuyển NumPy array sang PyTorch tensor:

```python
import numpy as np
import torch

arr = np.array([1, 2, 3])

tensor = torch.from_numpy(arr)

print(tensor)
```

Chuyển PyTorch tensor sang NumPy array:

```python
import torch

tensor = torch.tensor([1, 2, 3])

arr = tensor.numpy()

print(arr)
```

Nếu tensor nằm trên GPU, cần đưa về CPU trước:

```python
arr = tensor.cpu().numpy()
```

---

## 41. Một số lỗi thường gặp khi học NumPy

### Lỗi 1: Nhầm list Python với NumPy array

```python
a = [1, 2, 3]

print(a * 2)
```

Kết quả:

```txt
[1, 2, 3, 1, 2, 3]
```

Với NumPy:

```python
a = np.array([1, 2, 3])

print(a * 2)
```

Kết quả:

```txt
[2 4 6]
```

---

### Lỗi 2: Nhầm nhân từng phần tử với nhân ma trận

```python
A * B
```

là nhân từng phần tử.

Muốn nhân ma trận, dùng:

```python
A @ B
```

hoặc:

```python
np.matmul(A, B)
```

---

### Lỗi 3: Sai shape khi reshape

```python
arr = np.array([1, 2, 3, 4, 5, 6])

arr.reshape(4, 4)
```

Sai vì 6 phần tử không thể reshape thành 16 phần tử.

---

### Lỗi 4: Nhầm `axis=0` và `axis=1`

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])
```

```python
np.sum(matrix, axis=0)
```

Kết quả:

```txt
[5 7 9]
```

Tính theo cột.

```python
np.sum(matrix, axis=1)
```

Kết quả:

```txt
[ 6 15]
```

Tính theo dòng.

---

### Lỗi 5: Dùng `and`, `or` thay vì `&`, `|`

Sai:

```python
arr[(arr > 3) and (arr < 8)]
```

Đúng:

```python
arr[(arr > 3) & (arr < 8)]
```

Trong NumPy:

```txt
& là AND
| là OR
~ là NOT
```

---

### Lỗi 6: Quên ngoặc khi lọc nhiều điều kiện

Sai:

```python
arr[arr > 3 & arr < 8]
```

Đúng:

```python
arr[(arr > 3) & (arr < 8)]
```

---

## 42. Bài tập luyện tập

### Bài 1

Tạo một NumPy array gồm các số từ 1 đến 10.

Yêu cầu:

```txt
in ra array
in ra shape
in ra số chiều
in ra tổng số phần tử
```

---

### Bài 2

Tạo một ma trận 3 x 3 gồm các số từ 1 đến 9.

Yêu cầu:

```txt
in ra ma trận
in ra dòng đầu tiên
in ra cột thứ hai
in ra phần tử ở dòng 2, cột 2
```

---

### Bài 3

Tạo array:

```python
arr = np.array([5, 10, 15, 20, 25, 30])
```

Yêu cầu:

```txt
lọc các phần tử lớn hơn 15
lọc các phần tử chia hết cho 10
thay các phần tử nhỏ hơn 20 bằng 0
```

---

### Bài 4

Tạo ma trận:

```python
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
])
```

Yêu cầu:

```txt
tính tổng toàn bộ ma trận
tính tổng theo từng cột
tính tổng theo từng dòng
tính trung bình toàn bộ ma trận
```

---

### Bài 5

Tạo hai ma trận:

```python
A = np.array([
    [1, 2],
    [3, 4]
])

B = np.array([
    [5, 6],
    [7, 8]
])
```

Yêu cầu:

```txt
tính A + B
tính A - B
tính A * B
tính A @ B
tính chuyển vị của A
tính định thức của A
tính nghịch đảo của A
```

---

### Bài 6

Giải hệ phương trình tuyến tính:

```txt
x + 2y = 5
3x + 4y = 11
```

bằng `np.linalg.solve`.

---

### Bài 7

Tạo dữ liệu:

```python
data = np.array([10, 20, 30, 40, 50])
```

Yêu cầu:

```txt
tính trung bình
tính phương sai
tính độ lệch chuẩn
chuẩn hóa dữ liệu theo công thức z-score
```

---

### Bài 8

Tạo dữ liệu x từ -10 đến 10 gồm 100 điểm.

Yêu cầu:

```txt
tính y = x^2
vẽ đồ thị bằng Matplotlib
```

---

## 43. Tóm tắt các lệnh NumPy quan trọng

### Import

```python
import numpy as np
```

### Tạo array

```python
np.array()
np.zeros()
np.ones()
np.full()
np.eye()
np.arange()
np.linspace()
np.random.rand()
np.random.randint()
```

### Thuộc tính

```python
arr.shape
arr.ndim
arr.size
arr.dtype
```

### Reshape

```python
arr.reshape()
arr.flatten()
arr.ravel()
```

### Tính toán

```python
np.sum()
np.mean()
np.median()
np.max()
np.min()
np.std()
np.var()
```

### Điều kiện

```python
arr[arr > 0]
np.where()
```

### Sắp xếp

```python
np.sort()
```

### Nối và tách

```python
np.concatenate()
np.vstack()
np.hstack()
np.split()
np.hsplit()
np.vsplit()
```

### Đại số tuyến tính

```python
A @ B
np.dot()
np.matmul()
A.T
np.linalg.det()
np.linalg.inv()
np.linalg.solve()
np.linalg.eig()
np.linalg.norm()
```

---

## 44. Tóm tắt cuối

NumPy là thư viện nền tảng để xử lý dữ liệu số trong Python.

Đối tượng chính của NumPy là:

```txt
ndarray
```

NumPy phù hợp để làm việc với:

```txt
mảng
vector
ma trận
tensor
đại số tuyến tính
thống kê
xử lý ảnh
xử lý tín hiệu
mô phỏng toán học
Data Science
Machine Learning
Deep Learning
```

Cần nhớ:

```txt
NumPy array khác list Python.
NumPy hỗ trợ vectorization.
NumPy giúp tính toán nhanh hơn trên dữ liệu số.
NumPy rất mạnh với ma trận và đại số tuyến tính.
NumPy thường được dùng chung với Pandas, Matplotlib, Scikit-learn, PyTorch.
```

Phân biệt nhanh:

```txt
NumPy:
Xử lý mảng số, vector, ma trận.

Pandas:
Xử lý dữ liệu dạng bảng.

Matplotlib:
Vẽ biểu đồ.

PyTorch:
Xử lý tensor và huấn luyện mô hình AI.
```

Có thể hiểu đơn giản:

```txt
Nếu dữ liệu có thể biểu diễn bằng số, vector, ma trận hoặc tensor,
thì NumPy là một trong những công cụ đầu tiên nên nghĩ tới trong Python.
```
