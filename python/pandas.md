# Pandas trong Python

## 1. Pandas là gì?

**Pandas** là thư viện Python dùng để xử lý, phân tích và biến đổi dữ liệu dạng bảng.

Nếu NumPy mạnh về:

```txt
array
vector
matrix
tensor
```

thì Pandas mạnh về:

```txt
bảng dữ liệu
hàng và cột
file CSV
file Excel
dữ liệu thống kê
dataset trong Data Science
```

Cách import Pandas thường dùng:

```python
import pandas as pd
```

Ví dụ đầu tiên:

```python
import pandas as pd

data = {
    "name": ["An", "Binh", "Chi"],
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
1  Binh   21    9.0
2   Chi   19    7.5
```

Có thể hiểu đơn giản:

```txt
Pandas là công cụ chính để làm việc với dữ liệu dạng bảng trong Python.
```

---

## 2. Vì sao cần Pandas?

Trong thực tế, dữ liệu thường được lưu dưới dạng:

```txt
file CSV
file Excel
file JSON
bảng SQL
dataset từ Kaggle
log hệ thống
dữ liệu thống kê
dữ liệu khảo sát
```

Nếu chỉ dùng list hoặc NumPy array thì việc xử lý dữ liệu dạng bảng sẽ khá bất tiện, vì dữ liệu thực tế thường có:

```txt
tên cột
nhiều kiểu dữ liệu khác nhau
dữ liệu thiếu
dữ liệu trùng lặp
dữ liệu cần lọc
dữ liệu cần nhóm
dữ liệu cần thống kê
dữ liệu cần sắp xếp
```

Pandas giúp ta:

```txt
đọc dữ liệu từ file
xem dữ liệu nhanh
chọn dòng, chọn cột
lọc dữ liệu theo điều kiện
xử lý dữ liệu thiếu
xóa dữ liệu trùng
sắp xếp dữ liệu
nhóm dữ liệu
thống kê dữ liệu
biến đổi dữ liệu
chuẩn bị dữ liệu cho Machine Learning
```

---

## 3. Hai kiểu dữ liệu quan trọng trong Pandas

Pandas có hai kiểu dữ liệu chính:

```txt
Series
DataFrame
```

Có thể hiểu:

```txt
Series    giống một cột dữ liệu
DataFrame giống một bảng dữ liệu
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

Series có thể có index tùy chỉnh:

```python
scores = pd.Series(
    [8, 9, 7],
    index=["An", "Binh", "Chi"]
)

print(scores)
```

Kết quả:

```txt
An      8
Binh    9
Chi     7
dtype: int64
```

Truy cập dữ liệu trong Series:

```python
print(scores["An"])
```

Kết quả:

```txt
8
```

---

## 5. DataFrame là gì?

**DataFrame** là dữ liệu hai chiều, gồm nhiều hàng và nhiều cột.

DataFrame giống như:

```txt
bảng Excel
bảng SQL
dataset trong Machine Learning
```

Ví dụ:

```python
import pandas as pd

data = {
    "name": ["An", "Binh", "Chi"],
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
1  Binh   21    9.0
2   Chi   19    7.5
```

Trong DataFrame:

```txt
mỗi cột là một Series
mỗi dòng là một bản ghi
mỗi cột có tên cột
mỗi dòng có index
```

---

## 6. Tạo DataFrame

### 6.1. Tạo DataFrame từ dictionary

```python
import pandas as pd

data = {
    "name": ["An", "Binh", "Chi"],
    "age": [20, 21, 19],
    "score": [8.5, 9.0, 7.5]
}

df = pd.DataFrame(data)

print(df)
```

---

### 6.2. Tạo DataFrame từ list các dictionary

```python
data = [
    {"name": "An", "age": 20, "score": 8.5},
    {"name": "Binh", "age": 21, "score": 9.0},
    {"name": "Chi", "age": 19, "score": 7.5}
]

df = pd.DataFrame(data)

print(df)
```

---

### 6.3. Tạo DataFrame từ list hai chiều

```python
data = [
    ["An", 20, 8.5],
    ["Binh", 21, 9.0],
    ["Chi", 19, 7.5]
]

df = pd.DataFrame(data, columns=["name", "age", "score"])

print(df)
```

---

## 7. Đọc dữ liệu từ file CSV

Một trong những việc phổ biến nhất khi dùng Pandas là đọc file CSV.

```python
import pandas as pd

df = pd.read_csv("students.csv")

print(df)
```

Ví dụ file `students.csv`:

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

Nếu file CSV dùng dấu `;` thay vì dấu `,`, dùng:

```python
df = pd.read_csv("students.csv", sep=";")
```

Nếu file có tiếng Việt bị lỗi encoding, có thể thử:

```python
df = pd.read_csv("students.csv", encoding="utf-8")
```

hoặc:

```python
df = pd.read_csv("students.csv", encoding="latin1")
```

---

## 8. Đọc dữ liệu từ file Excel

```python
import pandas as pd

df = pd.read_excel("students.xlsx")

print(df)
```

Đọc một sheet cụ thể:

```python
df = pd.read_excel("students.xlsx", sheet_name="Sheet1")
```

---

## 9. Ghi dữ liệu ra file

Ghi ra CSV:

```python
df.to_csv("output.csv", index=False)
```

Ghi ra Excel:

```python
df.to_excel("output.xlsx", index=False)
```

Ý nghĩa:

```txt
index=False nghĩa là không ghi cột index ra file.
```

Nếu không dùng `index=False`, Pandas sẽ ghi thêm cột index vào file.

---

## 10. Xem nhanh dữ liệu

Sau khi đọc dữ liệu, ta thường cần xem tổng quan dữ liệu.

### 10.1. Xem 5 dòng đầu

```python
df.head()
```

Xem 10 dòng đầu:

```python
df.head(10)
```

---

### 10.2. Xem 5 dòng cuối

```python
df.tail()
```

Xem 10 dòng cuối:

```python
df.tail(10)
```

---

### 10.3. Xem thông tin tổng quan

```python
df.info()
```

Lệnh này cho biết:

```txt
số dòng
số cột
tên cột
số giá trị không bị thiếu
kiểu dữ liệu của từng cột
dung lượng bộ nhớ
```

---

### 10.4. Xem thống kê cơ bản

```python
df.describe()
```

Lệnh này thống kê các cột số:

```txt
count
mean
std
min
25%
50%
75%
max
```

Nếu muốn thống kê cả cột dạng chữ:

```python
df.describe(include="all")
```

---

## 11. Các thuộc tính quan trọng của DataFrame

Ví dụ:

```python
import pandas as pd

data = {
    "name": ["An", "Binh", "Chi"],
    "age": [20, 21, 19],
    "score": [8.5, 9.0, 7.5]
}

df = pd.DataFrame(data)
```

### 11.1. Xem kích thước

```python
df.shape
```

Kết quả:

```txt
(3, 3)
```

Nghĩa là:

```txt
3 dòng
3 cột
```

---

### 11.2. Xem tên cột

```python
df.columns
```

---

### 11.3. Xem index

```python
df.index
```

---

### 11.4. Xem kiểu dữ liệu từng cột

```python
df.dtypes
```

---

### 11.5. Xem số phần tử

```python
df.size
```

---

## 12. Chọn cột trong DataFrame

### 12.1. Chọn một cột

```python
df["name"]
```

Kết quả là một Series.

---

### 12.2. Chọn nhiều cột

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

## 13. Chọn dòng bằng `loc` và `iloc`

Pandas có hai cách chọn dữ liệu rất quan trọng:

```txt
loc
iloc
```

Cách nhớ:

```txt
loc  chọn theo label hoặc tên index
iloc chọn theo vị trí số nguyên
```

---

### 13.1. Dùng `loc`

```python
df.loc[0]
```

Lấy dòng có index là `0`.

Lấy giá trị ở dòng index `0`, cột `"name"`:

```python
df.loc[0, "name"]
```

Lấy nhiều dòng và nhiều cột:

```python
df.loc[0:2, ["name", "score"]]
```

Lưu ý: với `loc`, lát cắt `0:2` thường lấy cả index `2`.

---

### 13.2. Dùng `iloc`

```python
df.iloc[0]
```

Lấy dòng đầu tiên theo vị trí.

Lấy giá trị ở dòng đầu tiên, cột thứ hai:

```python
df.iloc[0, 1]
```

Lấy nhiều dòng và nhiều cột:

```python
df.iloc[0:2, 0:2]
```

Lưu ý: với `iloc`, lát cắt `0:2` lấy vị trí 0 và 1, không lấy vị trí 2.

---

## 14. Lọc dữ liệu theo điều kiện

Ví dụ:

```python
data = {
    "name": ["An", "Binh", "Chi", "Dung"],
    "age": [20, 21, 19, 22],
    "score": [8.5, 9.0, 7.5, 4.0]
}

df = pd.DataFrame(data)
```

Lọc sinh viên có điểm từ 8 trở lên:

```python
df[df["score"] >= 8]
```

Lọc sinh viên tuổi lớn hơn 20:

```python
df[df["age"] > 20]
```

Lọc nhiều điều kiện:

```python
df[(df["score"] >= 8) & (df["age"] >= 20)]
```

Trong Pandas:

```txt
& là AND
| là OR
~ là NOT
```

Phải đặt từng điều kiện trong dấu ngoặc:

```python
(df["score"] >= 8) & (df["age"] >= 20)
```

---

## 15. Lọc dữ liệu với `isin`

`isin` dùng để lọc các dòng có giá trị nằm trong một danh sách.

Ví dụ:

```python
df[df["name"].isin(["An", "Chi"])]
```

Lọc các sinh viên có tên là An hoặc Chi.

---

## 16. Lọc dữ liệu với chuỗi

Ví dụ:

```python
df[df["name"].str.contains("An")]
```

Lọc các dòng mà cột `name` có chứa chuỗi `"An"`.

Không phân biệt hoa thường:

```python
df[df["name"].str.contains("an", case=False)]
```

Lọc tên bắt đầu bằng chữ A:

```python
df[df["name"].str.startswith("A")]
```

Lọc tên kết thúc bằng chữ n:

```python
df[df["name"].str.endswith("n")]
```

---

## 17. Thêm cột mới

Thêm cột `passed`:

```python
df["passed"] = df["score"] >= 5
```

Thêm cột điểm cộng:

```python
df["bonus_score"] = df["score"] + 0.5
```

Thêm cột phân loại:

```python
df["level"] = ["Good", "Excellent", "Good", "Fail"]
```

---

## 18. Cập nhật giá trị trong DataFrame

Cập nhật một ô dữ liệu:

```python
df.loc[0, "score"] = 9.5
```

Cập nhật nhiều dòng theo điều kiện:

```python
df.loc[df["score"] < 5, "passed"] = False
```

Ví dụ:

```python
df.loc[df["score"] >= 5, "passed"] = True
df.loc[df["score"] < 5, "passed"] = False
```

---

## 19. Xóa cột và xóa dòng

### 19.1. Xóa cột

```python
df = df.drop(columns=["passed"])
```

Xóa nhiều cột:

```python
df = df.drop(columns=["passed", "bonus_score"])
```

---

### 19.2. Xóa dòng theo index

```python
df = df.drop(index=0)
```

Xóa nhiều dòng:

```python
df = df.drop(index=[0, 2])
```

---

## 20. Đổi tên cột

```python
df = df.rename(columns={
    "name": "student_name",
    "score": "final_score"
})
```

Đổi tên cột giúp dữ liệu dễ hiểu hơn.

---

## 21. Sắp xếp dữ liệu

Sắp xếp theo điểm tăng dần:

```python
df.sort_values(by="score")
```

Sắp xếp theo điểm giảm dần:

```python
df.sort_values(by="score", ascending=False)
```

Sắp xếp theo nhiều cột:

```python
df.sort_values(by=["age", "score"], ascending=[True, False])
```

Nếu muốn lưu kết quả:

```python
df = df.sort_values(by="score", ascending=False)
```

---

## 22. Reset index

Sau khi lọc hoặc sắp xếp, index có thể bị lộn xộn.

Reset index:

```python
df = df.reset_index(drop=True)
```

Ý nghĩa:

```txt
reset_index: đánh lại index từ 0
drop=True: bỏ index cũ
```

---

## 23. Xử lý dữ liệu thiếu

Dữ liệu thiếu thường được biểu diễn là:

```txt
NaN
```

Ví dụ:

```python
import pandas as pd
import numpy as np

data = {
    "name": ["An", "Binh", "Chi", "Dung"],
    "age": [20, np.nan, 19, 22],
    "score": [8.5, 9.0, np.nan, 4.0]
}

df = pd.DataFrame(data)
```

---

### 23.1. Kiểm tra dữ liệu thiếu

```python
df.isnull()
```

Đếm số giá trị thiếu theo từng cột:

```python
df.isnull().sum()
```

Kiểm tra dòng nào có dữ liệu thiếu:

```python
df[df.isnull().any(axis=1)]
```

---

### 23.2. Xóa dữ liệu thiếu

Xóa các dòng có dữ liệu thiếu:

```python
df = df.dropna()
```

Xóa các cột có dữ liệu thiếu:

```python
df = df.dropna(axis=1)
```

---

### 23.3. Điền dữ liệu thiếu

Điền bằng 0:

```python
df["score"] = df["score"].fillna(0)
```

Điền bằng giá trị trung bình:

```python
df["score"] = df["score"].fillna(df["score"].mean())
```

Điền bằng trung vị:

```python
df["score"] = df["score"].fillna(df["score"].median())
```

Điền bằng giá trị xuất hiện nhiều nhất:

```python
df["name"] = df["name"].fillna(df["name"].mode()[0])
```

---

## 24. Xử lý dữ liệu trùng lặp

Kiểm tra dòng trùng:

```python
df.duplicated()
```

Đếm số dòng trùng:

```python
df.duplicated().sum()
```

Xóa dòng trùng:

```python
df = df.drop_duplicates()
```

Xóa dòng trùng theo một cột:

```python
df = df.drop_duplicates(subset=["name"])
```

---

## 25. Thống kê dữ liệu

Một số hàm thống kê thường dùng:

```python
df["score"].mean()
df["score"].median()
df["score"].max()
df["score"].min()
df["score"].sum()
df["score"].std()
df["score"].var()
df["score"].count()
```

Ý nghĩa:

```txt
mean    trung bình
median  trung vị
max     giá trị lớn nhất
min     giá trị nhỏ nhất
sum     tổng
std     độ lệch chuẩn
var     phương sai
count   số giá trị không bị thiếu
```

---

## 26. Đếm giá trị với `value_counts`

```python
df["score"].value_counts()
```

Ví dụ với cột `class`:

```python
df["class"].value_counts()
```

Dùng để đếm mỗi lớp có bao nhiêu sinh viên.

Tính tỷ lệ phần trăm:

```python
df["class"].value_counts(normalize=True)
```

---

## 27. GroupBy là gì?

`groupby` dùng để nhóm dữ liệu theo một hoặc nhiều cột.

Có thể hiểu giống `GROUP BY` trong SQL.

Ví dụ:

```python
data = {
    "class": ["A", "A", "B", "B", "C"],
    "name": ["An", "Binh", "Chi", "Dung", "Em"],
    "score": [8, 9, 7, 6, 10]
}

df = pd.DataFrame(data)
```

Tính điểm trung bình theo từng lớp:

```python
df.groupby("class")["score"].mean()
```

Kết quả:

```txt
class
A     8.5
B     6.5
C    10.0
Name: score, dtype: float64
```

Tính nhiều thống kê:

```python
df.groupby("class")["score"].agg(["mean", "max", "min", "count"])
```

Group theo nhiều cột:

```python
df.groupby(["class", "gender"])["score"].mean()
```

---

## 28. Apply, map và lambda

### 28.1. Dùng `apply`

`apply` dùng để áp dụng một hàm lên dữ liệu.

Ví dụ:

```python
def classify(score):
    if score >= 8:
        return "Good"
    elif score >= 5:
        return "Average"
    else:
        return "Fail"

df["level"] = df["score"].apply(classify)
```

---

### 28.2. Dùng `lambda`

Viết ngắn hơn:

```python
df["passed"] = df["score"].apply(lambda x: x >= 5)
```

---

### 28.3. Dùng `map`

`map` thường dùng để thay thế giá trị trong Series.

```python
df["passed_text"] = df["passed"].map({
    True: "Passed",
    False: "Failed"
})
```

---

## 29. Làm việc với chuỗi trong Pandas

Pandas hỗ trợ xử lý chuỗi qua `.str`.

Ví dụ:

```python
df["name"].str.lower()
df["name"].str.upper()
df["name"].str.strip()
df["name"].str.len()
```

Ý nghĩa:

```txt
lower: chuyển thành chữ thường
upper: chuyển thành chữ hoa
strip: xóa khoảng trắng đầu và cuối
len: tính độ dài chuỗi
```

Tạo cột mới:

```python
df["name_lower"] = df["name"].str.lower()
```

Tách chuỗi:

```python
df["first_name"] = df["full_name"].str.split(" ").str[0]
```

---

## 30. Làm việc với thời gian

Pandas xử lý thời gian rất mạnh.

Ví dụ:

```python
df["date"] = pd.to_datetime(df["date"])
```

Sau đó có thể lấy năm, tháng, ngày:

```python
df["year"] = df["date"].dt.year
df["month"] = df["date"].dt.month
df["day"] = df["date"].dt.day
```

Lấy thứ trong tuần:

```python
df["weekday"] = df["date"].dt.day_name()
```

Lọc dữ liệu theo thời gian:

```python
df[df["date"] >= "2025-01-01"]
```

---

## 31. Kết hợp DataFrame

Pandas hỗ trợ nhiều cách kết hợp dữ liệu:

```txt
concat
merge
join
```

---

### 31.1. `concat`

`concat` dùng để nối DataFrame theo dòng hoặc cột.

Nối theo dòng:

```python
df_all = pd.concat([df1, df2], axis=0)
```

Nối theo cột:

```python
df_all = pd.concat([df1, df2], axis=1)
```

---

### 31.2. `merge`

`merge` giống JOIN trong SQL.

Ví dụ:

```python
students = pd.DataFrame({
    "student_id": [1, 2, 3],
    "name": ["An", "Binh", "Chi"]
})

scores = pd.DataFrame({
    "student_id": [1, 2, 3],
    "score": [8.5, 9.0, 7.5]
})

result = pd.merge(students, scores, on="student_id")

print(result)
```

Kết quả:

```txt
   student_id  name  score
0           1    An    8.5
1           2  Binh    9.0
2           3   Chi    7.5
```

Các kiểu merge thường gặp:

```txt
inner
left
right
outer
```

Ví dụ:

```python
pd.merge(students, scores, on="student_id", how="left")
```

---

## 32. Pivot table

Pivot table dùng để tổng hợp dữ liệu theo hàng và cột.

Ví dụ:

```python
data = {
    "class": ["A", "A", "B", "B"],
    "gender": ["M", "F", "M", "F"],
    "score": [8, 9, 7, 6]
}

df = pd.DataFrame(data)

pivot = pd.pivot_table(
    df,
    values="score",
    index="class",
    columns="gender",
    aggfunc="mean"
)

print(pivot)
```

Pivot table thường dùng để làm báo cáo dữ liệu.

---

## 33. Biến đổi dữ liệu với `melt`

`melt` dùng để chuyển dữ liệu từ dạng rộng sang dạng dài.

Ví dụ:

```python
df = pd.DataFrame({
    "name": ["An", "Binh"],
    "math": [8, 9],
    "physics": [7, 8]
})

long_df = df.melt(
    id_vars="name",
    value_vars=["math", "physics"],
    var_name="subject",
    value_name="score"
)

print(long_df)
```

Kết quả:

```txt
   name  subject  score
0    An     math      8
1  Binh     math      9
2    An  physics      7
3  Binh  physics      8
```

---

## 34. Kết hợp Pandas với NumPy

Pandas thường dùng chung với NumPy.

Ví dụ:

```python
import pandas as pd
import numpy as np

df = pd.DataFrame({
    "score": [8, 9, np.nan, 7]
})

df["score"] = df["score"].fillna(np.mean(df["score"]))

print(df)
```

Chuyển DataFrame sang NumPy array:

```python
arr = df.to_numpy()
```

Chuyển NumPy array sang DataFrame:

```python
df = pd.DataFrame(arr, columns=["col1", "col2"])
```

---

## 35. Kết hợp Pandas với Matplotlib

Pandas thường dùng để xử lý dữ liệu, Matplotlib dùng để vẽ biểu đồ.

Ví dụ:

```python
import pandas as pd
import matplotlib.pyplot as plt

data = {
    "name": ["An", "Binh", "Chi"],
    "score": [8.5, 9.0, 7.5]
}

df = pd.DataFrame(data)

plt.bar(df["name"], df["score"])
plt.xlabel("Student")
plt.ylabel("Score")
plt.title("Student Scores")
plt.show()
```

Pandas cũng có thể vẽ nhanh:

```python
df.plot(x="name", y="score", kind="bar")
plt.show()
```

Các kiểu biểu đồ thường dùng:

```python
df.plot(kind="line")
df.plot(kind="bar")
df.plot(kind="hist")
df.plot(kind="scatter", x="age", y="score")
```

---

## 36. Pandas trong Data Science

Trong Data Science, Pandas thường dùng ở giai đoạn xử lý dữ liệu ban đầu.

Quy trình thường gặp:

```txt
1. Đọc dữ liệu
2. Xem tổng quan dữ liệu
3. Kiểm tra dữ liệu thiếu
4. Làm sạch dữ liệu
5. Lọc dữ liệu
6. Biến đổi dữ liệu
7. Thống kê dữ liệu
8. Trực quan hóa dữ liệu
9. Chuẩn bị dữ liệu cho mô hình Machine Learning
```

Ví dụ:

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df.head())
print(df.info())
print(df.describe())

print(df.isnull().sum())

df = df.drop_duplicates()
df["score"] = df["score"].fillna(df["score"].mean())
```

---

## 37. Pandas trong Machine Learning

Trước khi huấn luyện mô hình Machine Learning, dữ liệu thường phải được xử lý bằng Pandas.

Pandas thường dùng để:

```txt
đọc dataset
xóa cột không cần thiết
xử lý dữ liệu thiếu
mã hóa dữ liệu phân loại
chuẩn hóa dữ liệu
tách dữ liệu đầu vào X và nhãn y
```

Ví dụ tách X và y:

```python
df = pd.read_csv("students.csv")

X = df[["age", "study_hours"]]
y = df["score"]
```

Trong đó:

```txt
X là dữ liệu đầu vào
y là nhãn hoặc giá trị cần dự đoán
```

Chuyển sang NumPy array:

```python
X = X.to_numpy()
y = y.to_numpy()
```

---

## 38. Mã hóa dữ liệu phân loại

Machine Learning thường cần dữ liệu số, nhưng dữ liệu thực tế có thể có dạng chữ.

Ví dụ:

```python
df = pd.DataFrame({
    "gender": ["male", "female", "female", "male"]
})
```

Dùng `map`:

```python
df["gender_encoded"] = df["gender"].map({
    "male": 1,
    "female": 0
})
```

Dùng one-hot encoding:

```python
encoded = pd.get_dummies(df["gender"])

print(encoded)
```

Kết quả:

```txt
   female   male
0   False   True
1    True  False
2    True  False
3   False   True
```

Có thể nối lại vào DataFrame:

```python
df = pd.concat([df, encoded], axis=1)
```

---

## 39. Một số lỗi thường gặp khi học Pandas

### Lỗi 1: Nhầm một cột và nhiều cột

Một cột:

```python
df["name"]
```

Kết quả là Series.

Nhiều cột:

```python
df[["name", "score"]]
```

Kết quả là DataFrame.

Sai thường gặp:

```python
df["name", "score"]
```

Đúng:

```python
df[["name", "score"]]
```

---

### Lỗi 2: Quên ngoặc khi lọc nhiều điều kiện

Sai:

```python
df[df["score"] >= 8 & df["age"] >= 20]
```

Đúng:

```python
df[(df["score"] >= 8) & (df["age"] >= 20)]
```

---

### Lỗi 3: Dùng `and`, `or` thay vì `&`, `|`

Sai:

```python
df[(df["score"] >= 8) and (df["age"] >= 20)]
```

Đúng:

```python
df[(df["score"] >= 8) & (df["age"] >= 20)]
```

Trong Pandas:

```txt
& là AND
| là OR
~ là NOT
```

---

### Lỗi 4: Quên gán lại kết quả

Nhiều hàm Pandas không tự sửa DataFrame gốc nếu không gán lại.

Ví dụ:

```python
df.dropna()
```

Dòng này trả về DataFrame mới nhưng không lưu lại.

Đúng:

```python
df = df.dropna()
```

Hoặc dùng:

```python
df.dropna(inplace=True)
```

Tuy nhiên, cách gán lại thường rõ ràng hơn:

```python
df = df.dropna()
```

---

### Lỗi 5: Nhầm `loc` và `iloc`

```txt
loc  dùng label/index name
iloc dùng vị trí số nguyên
```

Ví dụ:

```python
df.loc[0, "name"]
```

lấy dòng có index `0`, cột `"name"`.

```python
df.iloc[0, 1]
```

lấy dòng đầu tiên, cột thứ hai.

---

### Lỗi 6: Lỗi `SettingWithCopyWarning`

Ví dụ dễ gây cảnh báo:

```python
filtered = df[df["score"] >= 8]
filtered["level"] = "Good"
```

Cách an toàn hơn:

```python
filtered = df[df["score"] >= 8].copy()
filtered["level"] = "Good"
```

Hoặc sửa trực tiếp trên DataFrame gốc:

```python
df.loc[df["score"] >= 8, "level"] = "Good"
```

---

## 40. Bài tập luyện tập

### Bài 1

Tạo DataFrame gồm thông tin sinh viên:

```txt
name
age
score
class
```

Yêu cầu:

```txt
in ra DataFrame
in 5 dòng đầu
in shape
in columns
in dtypes
```

---

### Bài 2

Từ DataFrame sinh viên, hãy:

```txt
chọn cột name
chọn hai cột name và score
chọn dòng đầu tiên bằng iloc
chọn dòng có index 0 bằng loc
```

---

### Bài 3

Lọc dữ liệu:

```txt
sinh viên có score >= 8
sinh viên có age > 20
sinh viên có score >= 8 và age >= 20
sinh viên thuộc class A hoặc class B
```

---

### Bài 4

Thêm cột:

```txt
passed = True nếu score >= 5
bonus_score = score + 0.5
level = Good nếu score >= 8, Average nếu score >= 5, Fail nếu score < 5
```

---

### Bài 5

Tạo DataFrame có dữ liệu thiếu.

Yêu cầu:

```txt
kiểm tra số giá trị thiếu mỗi cột
xóa dòng bị thiếu
điền score thiếu bằng trung bình
điền age thiếu bằng trung vị
```

---

### Bài 6

Tạo DataFrame có dòng trùng lặp.

Yêu cầu:

```txt
kiểm tra dòng trùng
đếm số dòng trùng
xóa dòng trùng
```

---

### Bài 7

Dùng `groupby` để:

```txt
tính điểm trung bình theo class
tính điểm cao nhất theo class
đếm số sinh viên theo class
```

---

### Bài 8

Đọc file `students.csv`, sau đó:

```txt
xem head
xem info
xem describe
kiểm tra missing values
lọc sinh viên điểm >= 8
ghi kết quả ra file good_students.csv
```

---

### Bài 9

Tạo hai DataFrame:

```txt
students: student_id, name
scores: student_id, score
```

Yêu cầu:

```txt
merge hai bảng theo student_id
```

---

### Bài 10

Tạo DataFrame gồm:

```txt
name
math
physics
chemistry
```

Yêu cầu:

```txt
tính điểm trung bình từng sinh viên
chuyển dữ liệu từ dạng rộng sang dạng dài bằng melt
```

---

## 41. Tóm tắt các lệnh Pandas quan trọng

### Import

```python
import pandas as pd
```

### Tạo dữ liệu

```python
pd.Series()
pd.DataFrame()
```

### Đọc file

```python
pd.read_csv()
pd.read_excel()
pd.read_json()
```

### Ghi file

```python
df.to_csv()
df.to_excel()
```

### Xem dữ liệu

```python
df.head()
df.tail()
df.info()
df.describe()
```

### Thuộc tính

```python
df.shape
df.columns
df.index
df.dtypes
df.size
```

### Chọn dữ liệu

```python
df["column"]
df[["col1", "col2"]]
df.loc[]
df.iloc[]
```

### Lọc dữ liệu

```python
df[df["column"] > value]
df[(condition1) & (condition2)]
df[(condition1) | (condition2)]
df[df["column"].isin([...])]
```

### Xử lý dữ liệu thiếu

```python
df.isnull()
df.isnull().sum()
df.dropna()
df.fillna()
```

### Xử lý trùng lặp

```python
df.duplicated()
df.drop_duplicates()
```

### Sắp xếp

```python
df.sort_values()
df.reset_index()
```

### Thống kê

```python
df.mean()
df.median()
df.max()
df.min()
df.sum()
df.std()
df.var()
df.count()
df.value_counts()
```

### Nhóm dữ liệu

```python
df.groupby()
df.agg()
```

### Biến đổi dữ liệu

```python
df.apply()
df.map()
pd.get_dummies()
```

### Kết hợp dữ liệu

```python
pd.concat()
pd.merge()
df.join()
```

### Pivot và melt

```python
pd.pivot_table()
df.melt()
```

---

## 42. Tóm tắt cuối

Pandas là thư viện Python dùng để xử lý và phân tích dữ liệu dạng bảng.

Đối tượng chính của Pandas là:

```txt
Series
DataFrame
```

Trong đó:

```txt
Series    giống một cột dữ liệu
DataFrame giống một bảng dữ liệu
```

Pandas phù hợp với:

```txt
file CSV
file Excel
dữ liệu dạng bảng
dữ liệu thống kê
dữ liệu khảo sát
dataset Machine Learning
dữ liệu cần làm sạch
dữ liệu cần phân tích
```

Cần nhớ:

```txt
Pandas dùng để đọc, xử lý, lọc, thống kê và biến đổi dữ liệu dạng bảng.
Pandas thường được dùng trước khi trực quan hóa dữ liệu hoặc huấn luyện mô hình Machine Learning.
Pandas thường đi chung với NumPy và Matplotlib.
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

Có thể hiểu đơn giản:

```txt
Nếu dữ liệu nằm trong bảng, file CSV, file Excel, hoặc dataset,
thì Pandas là công cụ đầu tiên nên nghĩ tới.
```
