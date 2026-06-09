# Pandas là gì?

## 1. Khái niệm

**Pandas** là thư viện Python dùng để xử lý và phân tích dữ liệu dạng bảng.

Nếu NumPy làm việc tốt với:

```txt
array
vector
matrix
tensor
```

thì Pandas làm việc tốt với dữ liệu dạng:

```txt
bảng
file CSV
file Excel
dữ liệu có hàng và cột
dữ liệu thống kê
dataset trong Data Science
```

Cách import Pandas thường dùng:

```python
import pandas as pd
```

Trong đó `pd` là tên viết tắt phổ biến của Pandas.

---

## 2. Vì sao cần Pandas?

Trong thực tế, dữ liệu thường không nằm sẵn dưới dạng mảng NumPy, mà thường nằm trong các file như:

```txt
.csv
.xlsx
.json
.sql
```

Pandas giúp ta:

```txt
đọc dữ liệu từ file
xem dữ liệu nhanh
lọc dữ liệu
chọn cột, chọn dòng
xử lý dữ liệu thiếu
thống kê dữ liệu
nhóm dữ liệu
sắp xếp dữ liệu
biến đổi dữ liệu
chuẩn bị dữ liệu cho Machine Learning
```

Có thể hiểu đơn giản:

```txt
Pandas là công cụ chính để làm việc với dữ liệu dạng bảng trong Python.
```

---

## 3. Hai kiểu dữ liệu quan trọng trong Pandas

Pandas có hai kiểu dữ liệu chính:

```txt
Series
DataFrame
```

---

## 4. Series là gì?

**Series** là dữ liệu một chiều, giống như một cột trong bảng.

Ví dụ:

```python
import pandas as pd

scores = pd.Series([8, 9, 7, 10])

print(scores)
```

Kết quả:

```txt
0     8
1     9
2     7
3    10
dtype: int64
```

Ở đây:

```txt
bên trái là index
bên phải là giá trị
```

Series có thể hiểu giống như:

```txt
một cột dữ liệu có chỉ số
```

---

## 5. DataFrame là gì?

**DataFrame** là dữ liệu hai chiều, giống như một bảng gồm nhiều hàng và nhiều cột.

Ví dụ:

```python
import pandas as pd

data = {
    "name": ["An", "Bình", "Chi"],
    "age": [20, 21, 19],
    "score": [8.5, 9.0, 7.5]
}

df = pd.DataFrame(data)

print(df)
```

Kết quả:

```txt
   name  age  score
0    An   20    8.5
1  Bình   21    9.0
2   Chi   19    7.5
```

DataFrame có thể hiểu giống như:

```txt
một bảng dữ liệu trong Excel hoặc SQL
```

---

## 6. Đọc dữ liệu từ file CSV

Một trong những việc phổ biến nhất khi dùng Pandas là đọc file CSV.

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df)
```

Ví dụ nếu file `students.csv` có nội dung:

```csv
name,age,score
An,20,8.5
Binh,21,9.0
Chi,19,7.5
```

Đọc file:

```python
df = pd.read_csv("students.csv")
print(df)
```

---

## 7. Xem nhanh dữ liệu

Sau khi đọc dữ liệu, ta thường cần xem trước dữ liệu.

```python
df.head()
```

Xem 5 dòng đầu.

```python
df.tail()
```

Xem 5 dòng cuối.

```python
df.info()
```

Xem thông tin tổng quan: số dòng, số cột, kiểu dữ liệu, dữ liệu thiếu.

```python
df.describe()
```

Xem thống kê cơ bản của các cột số: trung bình, độ lệch chuẩn, min, max.

Ví dụ:

```python
print(df.head())
print(df.info())
print(df.describe())
```

---

## 8. Một số thuộc tính quan trọng

```python
df.shape
```

Trả về số dòng và số cột.

Ví dụ:

```txt
(100, 5)
```

Nghĩa là DataFrame có 100 dòng và 5 cột.

```python
df.columns
```

Xem tên các cột.

```python
df.dtypes
```

Xem kiểu dữ liệu của từng cột.

```python
df.index
```

Xem index của DataFrame.

---

## 9. Chọn cột trong DataFrame

Chọn một cột:

```python
df["name"]
```

Kết quả là một Series.

Chọn nhiều cột:

```python
df[["name", "score"]]
```

Kết quả là một DataFrame.

Lưu ý:

```python
df["name"]
```

lấy một cột.

```python
df[["name", "score"]]
```

lấy nhiều cột.

---

## 10. Chọn dòng bằng loc và iloc

Pandas có hai cách chọn dòng quan trọng:

```txt
loc
iloc
```

### loc

`loc` dùng để chọn theo tên index hoặc điều kiện.

```python
df.loc[0]
```

Lấy dòng có index là `0`.

Chọn dòng và cột:

```python
df.loc[0, "name"]
```

Lấy giá trị ở dòng index `0`, cột `"name"`.

---

### iloc

`iloc` dùng để chọn theo vị trí số nguyên.

```python
df.iloc[0]
```

Lấy dòng đầu tiên.

```python
df.iloc[0, 1]
```

Lấy giá trị ở dòng đầu tiên, cột thứ hai.

Lưu ý:

```txt
loc  -> chọn theo label/index name
iloc -> chọn theo vị trí số nguyên
```

---

## 11. Lọc dữ liệu theo điều kiện

Ví dụ lọc sinh viên có điểm lớn hơn hoặc bằng 8:

```python
df[df["score"] >= 8]
```

Lọc sinh viên có tuổi lớn hơn 20:

```python
df[df["age"] > 20]
```

Lọc với nhiều điều kiện:

```python
df[(df["score"] >= 8) & (df["age"] >= 20)]
```

Lưu ý:

```txt
Trong Pandas:
& nghĩa là AND
| nghĩa là OR
~ nghĩa là NOT
```

Khi dùng nhiều điều kiện, nên đặt từng điều kiện trong dấu ngoặc `()`.

---

## 12. Thêm cột mới

Ví dụ thêm cột đánh giá kết quả:

```python
df["passed"] = df["score"] >= 5
```

Thêm cột điểm cộng:

```python
df["bonus_score"] = df["score"] + 0.5
```

---

## 13. Xóa cột

Xóa một cột:

```python
df = df.drop(columns=["passed"])
```

Xóa nhiều cột:

```python
df = df.drop(columns=["passed", "bonus_score"])
```

---

## 14. Sắp xếp dữ liệu

Sắp xếp theo điểm tăng dần:

```python
df.sort_values(by="score")
```

Sắp xếp theo điểm giảm dần:

```python
df.sort_values(by="score", ascending=False)
```

Nếu muốn lưu lại kết quả:

```python
df = df.sort_values(by="score", ascending=False)
```

---

## 15. Xử lý dữ liệu thiếu

Trong dữ liệu thực tế, có thể có giá trị bị thiếu, thường được biểu diễn là:

```txt
NaN
```

Kiểm tra dữ liệu thiếu:

```python
df.isnull()
```

Đếm số giá trị thiếu theo từng cột:

```python
df.isnull().sum()
```

Xóa các dòng có dữ liệu thiếu:

```python
df = df.dropna()
```

Điền giá trị thay thế cho dữ liệu thiếu:

```python
df["score"] = df["score"].fillna(0)
```

Hoặc điền bằng giá trị trung bình:

```python
df["score"] = df["score"].fillna(df["score"].mean())
```

---

## 16. Thống kê dữ liệu

Một số hàm thống kê thường dùng:

```python
df["score"].mean()
df["score"].max()
df["score"].min()
df["score"].sum()
df["score"].std()
df["score"].value_counts()
```

Ý nghĩa:

```txt
mean         trung bình
max          giá trị lớn nhất
min          giá trị nhỏ nhất
sum          tổng
std          độ lệch chuẩn
value_counts đếm số lần xuất hiện của từng giá trị
```

Ví dụ:

```python
print(df["score"].mean())
print(df["score"].max())
print(df["score"].value_counts())
```

---

## 17. GroupBy là gì?

`groupby` dùng để nhóm dữ liệu theo một hoặc nhiều cột.

Ví dụ có bảng điểm sinh viên theo lớp:

```python
data = {
    "class": ["A", "A", "B", "B", "C"],
    "name": ["An", "Bình", "Chi", "Dũng", "Em"],
    "score": [8, 9, 7, 6, 10]
}

df = pd.DataFrame(data)
```

Tính điểm trung bình theo từng lớp:

```python
df.groupby("class")["score"].mean()
```

Kết quả có thể là:

```txt
class
A    8.5
B    6.5
C   10.0
Name: score, dtype: float64
```

Có thể hiểu:

```txt
groupby giống GROUP BY trong SQL
```

---

## 18. Ghi dữ liệu ra file

Ghi ra file CSV:

```python
df.to_csv("output.csv", index=False)
```

Ghi ra file Excel:

```python
df.to_excel("output.xlsx", index=False)
```

Tham số:

```python
index=False
```

nghĩa là không ghi cột index ra file.

---

## 19. Pandas khác gì NumPy?

NumPy phù hợp với dữ liệu dạng mảng số:

```txt
array
vector
matrix
tensor
```

Pandas phù hợp với dữ liệu dạng bảng:

```txt
hàng
cột
tên cột
index
dữ liệu thiếu
dữ liệu từ CSV, Excel
```

Có thể hiểu đơn giản:

```txt
NumPy giống công cụ tính toán ma trận.
Pandas giống công cụ xử lý bảng dữ liệu.
```

Pandas thực chất cũng được xây dựng dựa trên NumPy ở bên dưới, nên hai thư viện này thường được học và dùng cùng nhau.

---

## 20. Ứng dụng của Pandas

Pandas được dùng nhiều trong:

```txt
Data Science
Machine Learning
phân tích dữ liệu
làm sạch dữ liệu
thống kê dữ liệu
xử lý file CSV, Excel
chuẩn bị dữ liệu trước khi train model
báo cáo dữ liệu
```

Ví dụ quy trình cơ bản trong Data Science:

```txt
1. Đọc dữ liệu bằng Pandas
2. Xem tổng quan dữ liệu
3. Xử lý dữ liệu thiếu
4. Lọc và biến đổi dữ liệu
5. Thống kê dữ liệu
6. Trực quan hóa dữ liệu
7. Đưa dữ liệu vào mô hình Machine Learning
```

---

## 21. Tóm tắt

Pandas là thư viện Python dùng để xử lý và phân tích dữ liệu dạng bảng.

Hai kiểu dữ liệu quan trọng nhất trong Pandas là:

```txt
Series
DataFrame
```

Trong đó:

```txt
Series    giống một cột dữ liệu
DataFrame giống một bảng dữ liệu
```

Một số lệnh cần nhớ:

```python
import pandas as pd

pd.Series()
pd.DataFrame()
pd.read_csv()
pd.read_excel()

df.head()
df.tail()
df.info()
df.describe()

df.shape
df.columns
df.dtypes

df["column"]
df[["col1", "col2"]]

df.loc[]
df.iloc[]

df.isnull().sum()
df.dropna()
df.fillna()

df.sort_values()
df.groupby()

df.to_csv()
df.to_excel()
```

Có thể nhớ ngắn gọn:

```txt
NumPy xử lý mảng số.
Pandas xử lý bảng dữ liệu.
PyTorch xử lý tensor để train AI.
```
