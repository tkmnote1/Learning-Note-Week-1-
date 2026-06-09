# Object-Oriented Programming trong Python

## 1. OOP là gì?

**OOP** là viết tắt của **Object-Oriented Programming**, nghĩa là **lập trình hướng đối tượng**.

Lập trình hướng đối tượng là cách lập trình trong đó ta tổ chức chương trình xoay quanh các **đối tượng**.

Mỗi đối tượng thường có:

```txt
1. Dữ liệu / thuộc tính
2. Hành vi / phương thức
```

Ví dụ ngoài đời thực:

```txt
Đối tượng: Student

Thuộc tính:
- name
- age
- student_id
- major

Hành vi:
- study()
- take_exam()
- show_info()
```

Trong Python, ta dùng **class** để mô tả loại đối tượng, sau đó tạo ra các **object** cụ thể từ class đó.

---

## 2. Vì sao cần OOP?

Nếu chương trình nhỏ, ta có thể viết bằng hàm bình thường.

Nhưng khi chương trình lớn hơn, có nhiều dữ liệu và nhiều chức năng liên quan đến nhau, OOP giúp code:

```txt
dễ tổ chức hơn
dễ đọc hơn
dễ tái sử dụng hơn
dễ mở rộng hơn
dễ bảo trì hơn
gần với cách con người mô hình hóa thế giới thực hơn
```

Ví dụ thay vì viết rời rạc:

```python
student_name = "An"
student_age = 20
student_score = 8.5

def show_student_info(name, age, score):
    print(name, age, score)
```

Ta có thể gom dữ liệu và hành vi vào một đối tượng:

```python
class Student:
    def __init__(self, name, age, score):
        self.name = name
        self.age = age
        self.score = score

    def show_info(self):
        print(self.name, self.age, self.score)
```

---

## 3. Class là gì?

**Class** là bản thiết kế để tạo ra object.

Có thể hiểu:

```txt
Class giống như bản thiết kế ngôi nhà.
Object giống như ngôi nhà thật được xây từ bản thiết kế đó.
```

Ví dụ:

```python
class Student:
    pass
```

Ở đây `Student` là một class.

Từ class này, ta có thể tạo object:

```python
s1 = Student()
s2 = Student()
```

`s1` và `s2` là hai object khác nhau được tạo ra từ class `Student`.

---

## 4. Object là gì?

**Object** là một đối tượng cụ thể được tạo ra từ class.

Ví dụ:

```python
class Student:
    pass

s1 = Student()
s2 = Student()

print(s1)
print(s2)
```

`s1` và `s2` là hai object khác nhau.

Mặc dù cùng được tạo từ class `Student`, nhưng mỗi object có thể có dữ liệu riêng.

---

## 5. Thuộc tính là gì?

**Thuộc tính** là dữ liệu gắn với object.

Ví dụ:

```python
class Student:
    pass

s1 = Student()

s1.name = "An"
s1.age = 20

print(s1.name)
print(s1.age)
```

Kết quả:

```txt
An
20
```

Ở đây:

```txt
name là thuộc tính
age là thuộc tính
s1 là object
```

Tuy nhiên, cách gán thuộc tính bên ngoài như trên không phải cách tốt nhất. Trong Python, ta thường khai báo thuộc tính trong hàm `__init__`.

---

## 6. Hàm `__init__` là gì?

`__init__` là hàm khởi tạo của class.

Nó tự động được gọi khi ta tạo object mới.

Ví dụ:

```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

s1 = Student("An", 20)

print(s1.name)
print(s1.age)
```

Kết quả:

```txt
An
20
```

Khi chạy dòng:

```python
s1 = Student("An", 20)
```

Python sẽ tự động gọi:

```python
__init__(self, name, age)
```

Trong đó:

```txt
self đại diện cho object đang được tạo
name nhận giá trị "An"
age nhận giá trị 20
```

---

## 7. `self` là gì?

`self` là tham số đại diện cho chính object hiện tại.

Ví dụ:

```python
class Student:
    def __init__(self, name):
        self.name = name

s1 = Student("An")
s2 = Student("Binh")
```

Ở đây:

```txt
self.name của s1 là "An"
self.name của s2 là "Binh"
```

`self` giúp mỗi object lưu dữ liệu riêng của nó.

Ví dụ đầy đủ:

```python
class Student:
    def __init__(self, name):
        self.name = name

    def say_hello(self):
        print("Hello, my name is", self.name)

s1 = Student("An")
s2 = Student("Binh")

s1.say_hello()
s2.say_hello()
```

Kết quả:

```txt
Hello, my name is An
Hello, my name is Binh
```

Nếu không có `self`, Python sẽ không biết đang dùng dữ liệu của object nào.

---

## 8. Phương thức là gì?

**Phương thức** là hàm được định nghĩa bên trong class.

Ví dụ:

```python
class Student:
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def show_info(self):
        print("Name:", self.name)
        print("Score:", self.score)

s1 = Student("An", 8.5)
s1.show_info()
```

Kết quả:

```txt
Name: An
Score: 8.5
```

Ở đây:

```txt
show_info là phương thức
```

Phương thức thường dùng để xử lý dữ liệu của object.

---

## 9. Ví dụ hoàn chỉnh đầu tiên

```python
class Student:
    def __init__(self, name, age, score):
        self.name = name
        self.age = age
        self.score = score

    def show_info(self):
        print("Name:", self.name)
        print("Age:", self.age)
        print("Score:", self.score)

    def is_passed(self):
        return self.score >= 5

s1 = Student("An", 20, 8.5)

s1.show_info()

if s1.is_passed():
    print("Passed")
else:
    print("Failed")
```

Kết quả:

```txt
Name: An
Age: 20
Score: 8.5
Passed
```

---

## 10. Class attribute và instance attribute

Trong Python OOP có hai loại thuộc tính quan trọng:

```txt
instance attribute
class attribute
```

---

### 10.1. Instance attribute

**Instance attribute** là thuộc tính riêng của từng object.

Ví dụ:

```python
class Student:
    def __init__(self, name):
        self.name = name

s1 = Student("An")
s2 = Student("Binh")

print(s1.name)
print(s2.name)
```

Kết quả:

```txt
An
Binh
```

Ở đây `name` là instance attribute, vì mỗi object có giá trị riêng.

---

### 10.2. Class attribute

**Class attribute** là thuộc tính dùng chung cho toàn bộ object của class.

Ví dụ:

```python
class Student:
    school = "UIT"

    def __init__(self, name):
        self.name = name

s1 = Student("An")
s2 = Student("Binh")

print(s1.school)
print(s2.school)
```

Kết quả:

```txt
UIT
UIT
```

Ở đây `school` là class attribute.

Nó thuộc về class `Student`, không thuộc riêng object nào.

---

## 11. Sự khác nhau giữa class attribute và instance attribute

Ví dụ:

```python
class Student:
    school = "UIT"

    def __init__(self, name):
        self.name = name

s1 = Student("An")
s2 = Student("Binh")

s1.name = "An Nguyen"
s1.school = "HCMUS"

print(s1.name)
print(s2.name)

print(s1.school)
print(s2.school)
print(Student.school)
```

Kết quả:

```txt
An Nguyen
Binh
HCMUS
UIT
UIT
```

Giải thích:

```txt
name là instance attribute, nên mỗi object có giá trị riêng.

school ban đầu là class attribute.
Nhưng khi gán s1.school = "HCMUS",
Python tạo một instance attribute mới tên school riêng cho s1.
Vì vậy s1.school khác Student.school.
```

Muốn đổi class attribute cho toàn bộ class, nên dùng:

```python
Student.school = "New School"
```

---

## 12. Constructor trong Python

Trong nhiều ngôn ngữ khác, hàm khởi tạo được gọi là **constructor**.

Trong Python, constructor thường được hiểu là:

```python
__init__()
```

Ví dụ:

```python
class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author

book1 = Book("Python Basic", "Nguyen Van A")
```

Khi tạo `book1`, hàm `__init__` tự động chạy để gán dữ liệu ban đầu.

---

## 13. Encapsulation là gì?

**Encapsulation** nghĩa là **đóng gói**.

Ý tưởng chính:

```txt
Gom dữ liệu và hành vi liên quan vào chung một class.
Hạn chế truy cập trực tiếp vào dữ liệu bên trong object.
```

Ví dụ không đóng gói tốt:

```python
class BankAccount:
    def __init__(self, balance):
        self.balance = balance

account = BankAccount(1000)
account.balance = -999999
```

Ở đây ta có thể gán `balance` thành số âm vô lý.

Cách tốt hơn:

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount

    def get_balance(self):
        return self.__balance

account = BankAccount(1000)

account.deposit(500)
account.withdraw(200)

print(account.get_balance())
```

Kết quả:

```txt
1300
```

Ở đây, người dùng object không nên sửa trực tiếp số dư. Họ phải đi qua các phương thức như `deposit`, `withdraw`, `get_balance`.

---

## 14. Private attribute trong Python

Python không có private tuyệt đối như một số ngôn ngữ khác.

Nhưng Python có quy ước:

```txt
_name      protected-like, không nên truy cập trực tiếp từ bên ngoài
__name     private-like, Python sẽ name mangling
```

Ví dụ:

```python
class Student:
    def __init__(self, name, score):
        self.name = name
        self.__score = score

    def get_score(self):
        return self.__score

s1 = Student("An", 8.5)

print(s1.name)
print(s1.get_score())
```

Không nên truy cập trực tiếp:

```python
print(s1.__score)
```

Dòng này sẽ lỗi:

```txt
AttributeError
```

Thực tế Python đổi tên `__score` thành dạng gần giống:

```txt
_Student__score
```

Đây gọi là **name mangling**.

---

## 15. Getter và Setter

Getter dùng để lấy dữ liệu.

Setter dùng để thay đổi dữ liệu có kiểm soát.

Ví dụ:

```python
class Student:
    def __init__(self, name, score):
        self.name = name
        self.__score = score

    def get_score(self):
        return self.__score

    def set_score(self, score):
        if 0 <= score <= 10:
            self.__score = score
        else:
            print("Invalid score")

s1 = Student("An", 8)

print(s1.get_score())

s1.set_score(9)
print(s1.get_score())

s1.set_score(15)
```

Kết quả:

```txt
8
9
Invalid score
```

Mục đích của setter là bảo vệ dữ liệu không bị gán sai.

---

## 16. Property trong Python

Python có `@property` giúp dùng getter và setter đẹp hơn.

Ví dụ:

```python
class Student:
    def __init__(self, name, score):
        self.name = name
        self.__score = score

    @property
    def score(self):
        return self.__score

    @score.setter
    def score(self, value):
        if 0 <= value <= 10:
            self.__score = value
        else:
            raise ValueError("Score must be between 0 and 10")

s1 = Student("An", 8)

print(s1.score)

s1.score = 9
print(s1.score)
```

Nhìn bên ngoài giống như truy cập thuộc tính:

```python
s1.score
```

Nhưng thực chất Python đang gọi getter.

Khi gán:

```python
s1.score = 9
```

Python đang gọi setter.

---

## 17. Inheritance là gì?

**Inheritance** nghĩa là **kế thừa**.

Kế thừa cho phép một class con nhận lại thuộc tính và phương thức từ class cha.

Ví dụ:

```python
class Person:
    def __init__(self, name):
        self.name = name

    def introduce(self):
        print("My name is", self.name)

class Student(Person):
    pass

s1 = Student("An")
s1.introduce()
```

Kết quả:

```txt
My name is An
```

Ở đây:

```txt
Person là class cha
Student là class con
Student kế thừa introduce() từ Person
```

---

## 18. Vì sao cần kế thừa?

Kế thừa giúp tái sử dụng code.

Ví dụ `Student` và `Teacher` đều là người, đều có `name`, `age`.

Ta có thể viết:

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def show_info(self):
        print("Name:", self.name)
        print("Age:", self.age)

class Student(Person):
    def __init__(self, name, age, student_id):
        super().__init__(name, age)
        self.student_id = student_id

class Teacher(Person):
    def __init__(self, name, age, department):
        super().__init__(name, age)
        self.department = department

s1 = Student("An", 20, "SV001")
t1 = Teacher("Dr. Binh", 40, "Software Engineering")

s1.show_info()
t1.show_info()
```

Nhờ kế thừa, ta không cần viết lại `name`, `age`, `show_info` cho từng class.

---

## 19. `super()` là gì?

`super()` dùng để gọi phương thức của class cha.

Ví dụ:

```python
class Person:
    def __init__(self, name):
        self.name = name

class Student(Person):
    def __init__(self, name, student_id):
        super().__init__(name)
        self.student_id = student_id

s1 = Student("An", "SV001")

print(s1.name)
print(s1.student_id)
```

Dòng:

```python
super().__init__(name)
```

gọi hàm `__init__` của class cha `Person`.

Nếu không gọi `super().__init__(name)`, thuộc tính `name` sẽ không được khởi tạo từ class cha.

---

## 20. Method overriding là gì?

**Method overriding** là khi class con định nghĩa lại phương thức đã có ở class cha.

Ví dụ:

```python
class Person:
    def introduce(self):
        print("I am a person")

class Student(Person):
    def introduce(self):
        print("I am a student")

p = Person()
s = Student()

p.introduce()
s.introduce()
```

Kết quả:

```txt
I am a person
I am a student
```

Class con `Student` đã ghi đè phương thức `introduce` của class cha `Person`.

---

## 21. Polymorphism là gì?

**Polymorphism** nghĩa là **đa hình**.

Ý tưởng:

```txt
Nhiều object khác nhau có thể cùng dùng một tên phương thức,
nhưng cách thực hiện có thể khác nhau.
```

Ví dụ:

```python
class Dog:
    def speak(self):
        print("Woof")

class Cat:
    def speak(self):
        print("Meow")

class Duck:
    def speak(self):
        print("Quack")

animals = [Dog(), Cat(), Duck()]

for animal in animals:
    animal.speak()
```

Kết quả:

```txt
Woof
Meow
Quack
```

Mặc dù đều gọi:

```python
animal.speak()
```

nhưng mỗi object phản ứng khác nhau.

Đây là đa hình.

---

## 22. Abstraction là gì?

**Abstraction** nghĩa là **trừu tượng hóa**.

Ý tưởng:

```txt
Ẩn đi chi tiết phức tạp bên trong.
Chỉ để lộ ra những gì cần thiết cho người dùng.
```

Ví dụ khi dùng điện thoại:

```txt
Người dùng chỉ cần bấm nút gọi.
Không cần biết bên trong xử lý sóng, mạng, tín hiệu như thế nào.
```

Trong OOP, abstraction thường thể hiện qua class và method.

Ví dụ:

```python
class CoffeeMachine:
    def make_coffee(self):
        self.__boil_water()
        self.__grind_coffee()
        self.__brew()

    def __boil_water(self):
        print("Boiling water")

    def __grind_coffee(self):
        print("Grinding coffee")

    def __brew(self):
        print("Brewing coffee")

machine = CoffeeMachine()
machine.make_coffee()
```

Người dùng chỉ cần gọi:

```python
machine.make_coffee()
```

Không cần quan tâm chi tiết bên trong.

---

## 23. Abstract class trong Python

Python hỗ trợ abstract class thông qua module `abc`.

Abstract class là class dùng làm khuôn mẫu, không nên tạo object trực tiếp.

Ví dụ:

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        print("Woof")

class Cat(Animal):
    def speak(self):
        print("Meow")

dog = Dog()
cat = Cat()

dog.speak()
cat.speak()
```

Nếu class con không cài đặt phương thức abstract, Python sẽ báo lỗi khi tạo object.

Ví dụ sai:

```python
class Bird(Animal):
    pass

bird = Bird()
```

Sẽ lỗi vì `Bird` chưa định nghĩa `speak`.

---

## 24. Bốn tính chất chính của OOP

OOP thường có 4 tính chất quan trọng:

```txt
1. Encapsulation - Đóng gói
2. Inheritance - Kế thừa
3. Polymorphism - Đa hình
4. Abstraction - Trừu tượng hóa
```

Tóm tắt:

```txt
Encapsulation:
Gom dữ liệu và hành vi vào class, bảo vệ dữ liệu bên trong.

Inheritance:
Class con kế thừa thuộc tính và phương thức từ class cha.

Polymorphism:
Cùng một tên phương thức, nhưng object khác nhau có cách thực hiện khác nhau.

Abstraction:
Ẩn chi tiết phức tạp, chỉ cung cấp giao diện cần thiết.
```

---

## 25. Static method

`@staticmethod` là phương thức thuộc class, nhưng không cần truy cập `self` hoặc `cls`.

Ví dụ:

```python
class MathUtils:
    @staticmethod
    def add(a, b):
        return a + b

print(MathUtils.add(3, 4))
```

Kết quả:

```txt
7
```

Static method thường dùng cho các hàm tiện ích liên quan đến class, nhưng không cần dữ liệu của object.

---

## 26. Class method

`@classmethod` là phương thức nhận tham số đầu tiên là `cls`, đại diện cho class.

Ví dụ:

```python
class Student:
    school = "UIT"

    def __init__(self, name):
        self.name = name

    @classmethod
    def change_school(cls, new_school):
        cls.school = new_school

Student.change_school("VNUHCM-UIT")

s1 = Student("An")
print(s1.school)
```

Kết quả:

```txt
VNUHCM-UIT
```

`classmethod` thường dùng khi cần thao tác với dữ liệu cấp class.

---

## 27. So sánh instance method, class method, static method

```txt
Instance method:
- Có self
- Làm việc với dữ liệu của object

Class method:
- Có cls
- Làm việc với dữ liệu của class

Static method:
- Không có self, không có cls
- Giống hàm bình thường đặt trong class cho hợp lý về mặt tổ chức
```

Ví dụ:

```python
class Example:
    class_value = 10

    def instance_method(self):
        print("This is instance method")

    @classmethod
    def class_method(cls):
        print("Class value:", cls.class_value)

    @staticmethod
    def static_method():
        print("This is static method")
```

---

## 28. Dunder method là gì?

Dunder method là các phương thức có hai dấu gạch dưới ở đầu và cuối tên.

Ví dụ:

```txt
__init__
__str__
__repr__
__len__
__add__
```

Dunder là viết tắt của:

```txt
double underscore
```

Các method này giúp object của ta tương tác tự nhiên hơn với Python.

---

## 29. `__str__` và `__repr__`

`__str__` dùng để định nghĩa cách object hiển thị khi dùng `print`.

Ví dụ:

```python
class Student:
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def __str__(self):
        return f"Student(name={self.name}, score={self.score})"

s1 = Student("An", 8.5)

print(s1)
```

Kết quả:

```txt
Student(name=An, score=8.5)
```

Nếu không có `__str__`, Python sẽ in ra dạng khó đọc như:

```txt
<__main__.Student object at 0x...>
```

`__repr__` thường dùng cho biểu diễn kỹ thuật, phục vụ debug.

Ví dụ:

```python
class Student:
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def __repr__(self):
        return f"Student({self.name!r}, {self.score!r})"
```

---

## 30. `__len__`

`__len__` cho phép dùng hàm `len()` với object.

Ví dụ:

```python
class Team:
    def __init__(self, members):
        self.members = members

    def __len__(self):
        return len(self.members)

team = Team(["An", "Binh", "Chi"])

print(len(team))
```

Kết quả:

```txt
3
```

---

## 31. `__add__`

`__add__` cho phép định nghĩa toán tử `+` cho object.

Ví dụ:

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)

    def __str__(self):
        return f"({self.x}, {self.y})"

v1 = Vector(1, 2)
v2 = Vector(3, 4)

v3 = v1 + v2

print(v3)
```

Kết quả:

```txt
(4, 6)
```

---

## 32. Composition là gì?

**Composition** nghĩa là một object chứa object khác.

Ví dụ:

```txt
Car có Engine
Student có Address
Order có nhiều OrderItem
```

Ví dụ code:

```python
class Engine:
    def start(self):
        print("Engine started")

class Car:
    def __init__(self):
        self.engine = Engine()

    def start(self):
        self.engine.start()
        print("Car started")

car = Car()
car.start()
```

Ở đây `Car` chứa một object `Engine`.

---

## 33. Inheritance vs Composition

Có hai cách thiết kế phổ biến:

```txt
Inheritance: A là một loại B
Composition: A có B
```

Ví dụ inheritance:

```txt
Student là một Person
Dog là một Animal
Car là một Vehicle
```

Ví dụ composition:

```txt
Car có Engine
Student có Address
Computer có CPU
```

Nên dùng kế thừa khi thật sự có quan hệ “là một”.

Nên dùng composition khi có quan hệ “có một”.

---

## 34. Ví dụ quản lý sinh viên

```python
class Student:
    def __init__(self, student_id, name, scores):
        self.student_id = student_id
        self.name = name
        self.scores = scores

    def average_score(self):
        return sum(self.scores) / len(self.scores)

    def is_passed(self):
        return self.average_score() >= 5

    def show_info(self):
        print("ID:", self.student_id)
        print("Name:", self.name)
        print("Average:", self.average_score())
        print("Passed:", self.is_passed())

s1 = Student("SV001", "An", [8, 7, 9])
s2 = Student("SV002", "Binh", [4, 5, 4])

s1.show_info()
s2.show_info()
```

---

## 35. Ví dụ quản lý tài khoản ngân hàng

```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.__balance = balance

    @property
    def balance(self):
        return self.__balance

    def deposit(self, amount):
        if amount <= 0:
            raise ValueError("Amount must be positive")
        self.__balance += amount

    def withdraw(self, amount):
        if amount <= 0:
            raise ValueError("Amount must be positive")

        if amount > self.__balance:
            raise ValueError("Not enough balance")

        self.__balance -= amount

    def __str__(self):
        return f"BankAccount(owner={self.owner}, balance={self.__balance})"

account = BankAccount("An", 1000)

account.deposit(500)
account.withdraw(300)

print(account.balance)
print(account)
```

---

## 36. Ví dụ kế thừa trong hệ thống nhân sự

```python
class Employee:
    def __init__(self, employee_id, name, base_salary):
        self.employee_id = employee_id
        self.name = name
        self.base_salary = base_salary

    def calculate_salary(self):
        return self.base_salary

    def show_info(self):
        print("ID:", self.employee_id)
        print("Name:", self.name)
        print("Salary:", self.calculate_salary())

class FullTimeEmployee(Employee):
    def __init__(self, employee_id, name, base_salary, bonus):
        super().__init__(employee_id, name, base_salary)
        self.bonus = bonus

    def calculate_salary(self):
        return self.base_salary + self.bonus

class PartTimeEmployee(Employee):
    def __init__(self, employee_id, name, hourly_rate, hours):
        super().__init__(employee_id, name, 0)
        self.hourly_rate = hourly_rate
        self.hours = hours

    def calculate_salary(self):
        return self.hourly_rate * self.hours

e1 = FullTimeEmployee("E001", "An", 1000, 200)
e2 = PartTimeEmployee("E002", "Binh", 10, 80)

employees = [e1, e2]

for employee in employees:
    employee.show_info()
```

Ở ví dụ này có đa hình vì cùng gọi:

```python
employee.calculate_salary()
```

nhưng mỗi loại nhân viên tính lương khác nhau.

---

## 37. OOP khác gì lập trình thủ tục?

Lập trình thủ tục thường tổ chức code theo hàm.

Ví dụ:

```python
def calculate_average(scores):
    return sum(scores) / len(scores)

def is_passed(scores):
    return calculate_average(scores) >= 5

student_name = "An"
student_scores = [8, 7, 9]
```

OOP tổ chức code theo object:

```python
class Student:
    def __init__(self, name, scores):
        self.name = name
        self.scores = scores

    def average_score(self):
        return sum(self.scores) / len(self.scores)

    def is_passed(self):
        return self.average_score() >= 5

student = Student("An", [8, 7, 9])
```

So sánh:

```txt
Lập trình thủ tục:
- Tập trung vào hàm
- Dữ liệu và hàm thường tách rời nhau

Lập trình hướng đối tượng:
- Tập trung vào object
- Dữ liệu và hành vi được gom vào cùng class
```

---

## 38. Khi nào nên dùng OOP?

Nên dùng OOP khi:

```txt
chương trình có nhiều loại đối tượng
mỗi đối tượng có dữ liệu và hành vi riêng
cần tái sử dụng code
cần mở rộng chương trình lâu dài
cần mô hình hóa bài toán thực tế
```

Ví dụ phù hợp với OOP:

```txt
quản lý sinh viên
quản lý thư viện
quản lý ngân hàng
game
website lớn
hệ thống bán hàng
mô phỏng thế giới thực
```

Không nhất thiết dùng OOP cho mọi thứ. Với các bài toán nhỏ, vài hàm đơn giản có thể đủ.

---

## 39. Một số lỗi thường gặp khi học OOP Python

### Lỗi 1: Quên `self`

Sai:

```python
class Student:
    def show_info():
        print("Hello")

s1 = Student()
s1.show_info()
```

Lỗi vì method của object cần có `self`.

Đúng:

```python
class Student:
    def show_info(self):
        print("Hello")

s1 = Student()
s1.show_info()
```

---

### Lỗi 2: Nhầm `self.name` với `name`

Sai:

```python
class Student:
    def __init__(self, name):
        name = name
```

Dòng này không lưu `name` vào object.

Đúng:

```python
class Student:
    def __init__(self, name):
        self.name = name
```

`self.name` là thuộc tính của object.

`name` chỉ là biến tham số trong hàm `__init__`.

---

### Lỗi 3: Gọi class mà thiếu tham số

```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

s1 = Student()
```

Lỗi vì `__init__` cần `name` và `age`.

Đúng:

```python
s1 = Student("An", 20)
```

---

### Lỗi 4: Nhầm class attribute với instance attribute

```python
class Student:
    scores = []

    def add_score(self, score):
        self.scores.append(score)

s1 = Student()
s2 = Student()

s1.add_score(10)

print(s2.scores)
```

Kết quả:

```txt
[10]
```

Điều này nguy hiểm vì `scores` là class attribute, được dùng chung.

Cách đúng:

```python
class Student:
    def __init__(self):
        self.scores = []

    def add_score(self, score):
        self.scores.append(score)
```

Mỗi object có list `scores` riêng.

---

## 40. Bài tập luyện tập

### Bài 1

Tạo class `Student` gồm:

```txt
name
age
score
```

Viết phương thức:

```txt
show_info()
is_passed()
```

Trong đó `is_passed()` trả về `True` nếu `score >= 5`.

---

### Bài 2

Tạo class `Rectangle` gồm:

```txt
width
height
```

Viết phương thức:

```txt
area()
perimeter()
```

---

### Bài 3

Tạo class `Circle` gồm:

```txt
radius
```

Viết phương thức:

```txt
area()
circumference()
```

---

### Bài 4

Tạo class `BankAccount` gồm:

```txt
owner
balance
```

Viết phương thức:

```txt
deposit(amount)
withdraw(amount)
show_balance()
```

Không cho rút tiền nếu số tiền rút lớn hơn balance.

---

### Bài 5

Tạo class `Book` gồm:

```txt
title
author
price
```

Viết phương thức `show_info()`.

Sau đó tạo class `EBook` kế thừa từ `Book`, có thêm thuộc tính:

```txt
file_size
```

Ghi đè phương thức `show_info()` để in thêm dung lượng file.

---

### Bài 6

Tạo class `Employee`, `FullTimeEmployee`, `PartTimeEmployee`.

Mỗi loại nhân viên có cách tính lương khác nhau.

Dùng đa hình để duyệt danh sách nhân viên và gọi `calculate_salary()`.

---

## 41. Tóm tắt

OOP là lập trình hướng đối tượng.

OOP tổ chức chương trình bằng cách gom dữ liệu và hành vi liên quan vào trong object.

Các khái niệm quan trọng:

```txt
Class:
Bản thiết kế để tạo object.

Object:
Đối tượng cụ thể được tạo ra từ class.

Attribute:
Dữ liệu của object.

Method:
Hành vi hoặc chức năng của object.

self:
Đại diện cho object hiện tại.

__init__:
Hàm khởi tạo, tự động chạy khi tạo object.

Encapsulation:
Đóng gói dữ liệu và hành vi, bảo vệ dữ liệu bên trong.

Inheritance:
Class con kế thừa class cha.

Polymorphism:
Cùng một tên phương thức, nhiều cách thực hiện khác nhau.

Abstraction:
Ẩn chi tiết phức tạp, chỉ đưa ra giao diện cần thiết.
```

Cách nhớ đơn giản:

```txt
Class là khuôn.
Object là sản phẩm tạo ra từ khuôn.
Attribute là dữ liệu của object.
Method là hành động của object.
self là chính object đang gọi phương thức.
```

Bốn tính chất chính của OOP:

```txt
1. Encapsulation
2. Inheritance
3. Polymorphism
4. Abstraction
```

Trong Python, OOP rất quan trọng vì nhiều thư viện lớn đều được thiết kế theo hướng đối tượng, ví dụ:

```txt
Pandas DataFrame
PyTorch model
Tkinter GUI
Django model
SQLAlchemy model
```

Hiểu tốt OOP sẽ giúp đọc code thư viện, viết project lớn và học framework dễ hơn.
