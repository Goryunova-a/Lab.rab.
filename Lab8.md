# Тема 8. Введение в ООП
Отчет по Теме #8 выполнила:
- Горюнова Алина Алексеевна
- ИВТ-22-1

| Задание | Лаб_раб | Сам_раб|
| ------ | ------ | ------|
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.


Лабораторные задания:	

1) Создайте класс "Car" с атрибутами производитель и модель. Создайте объект этого класса. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями.

```python
class Car: #класс Car представляет автомобиль
    def __init__(self, make, model): #метод __init__ служит для инициализации объекта
        self.make = make #присвоение значений свойствам объекта
        self.model = model
my_car = Car("Toyota", "Corolla") #создание объекта my_car класса Car, передавая параметры "Toyota" и  "Corolla"
#эти значения будут присвоены свойствам make  и model объекта my_car
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pic8/pic1.png)
- Данная программа создает класс 'Car' с атрибутами, после создаётся объект класса


2) Дополните код из первого задания, добавив в него атрибуты и методы класса, заставьте машину “поехать". Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
class Car: #класс Car представляет автомобиль
    def __init__(self, make, model): #метод __init__ служит для инициализации объекта
        self.make = make #присвоение значений свойствам объекта
        self.model = model
    def drive(self): # Метод drive описывает поведение автомобиля при вождении
        print(f"Driving the {self.make} {self.model}") # Вывод сообщения о том, какая машина управляется
my_car = Car("Toyota", "Corolla") #создание объекта my_car класса Car, передавая параметры "Toyota" и  "Corolla"
#эти значения будут присвоены свойствам make  и model объекта my_car
my_car.drive() # Вызов метода drive для объекта my_car
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pic8/pic2.png)
- Данная программа добавляет в программу из прошлого задания атрибуты и методы класса, заставляет машину “поехать"

3) Создайте новый класс "ElectricCar" с методом "charge" и атрибутом емкость батареи. Реализуйте его наследование от класса, созданного в первом задании. Заставьте машину поехать, а потом заряжаться.
Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.
```python
class Car: #класс Car представляет автомобиль
    def __init__(self, make, model): #метод __init__ служит для инициализации объекта
        self.make = make #присвоение значений свойствам объекта
        self.model = model
    def drive(self): # метод drive описывает поведение автомобиля при вождении
        print(f"Driving the {self.make} {self.model}") # вывод сообщения о том, какая машина управляется
my_car = Car("Toyota", "Corolla") #создание объекта my_car класса Car, передавая параметры "Toyota" и  "Corolla"
#эти значения будут присвоены свойствам make  и model объекта my_car
my_car.drive() # вызов метода drive для объекта my_car
class ElectricCar(Car): # класс ElectricCar представляет электромобиль
    def __init__(self, make, model, battery_capacity):# метод __init__ служит для инициализации объекта
        super().__init__(make, model)# наследуем свойства make и model от родительского класса Car
        self.battery_capacity = battery_capacity # присваиваем емкость аккумулятора свойству battery_capacity
        
    def charge(self):  # метод charge описывает процесс зарядки электромобиля
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh")# вывод сообщения о процессе зарядки 
my_electric_car = ElectricCar("Tesla", "Model X", 75) # создание объекта my_electric_car класса ElectricCar с параметрами "Tesla", "Model X" и 75
my_electric_car.drive() # вызов метода drive для объекта my_electric_car
my_electric_car.charge()  # вызов метода charge для объекта my_electric_car
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pic8/pic3.png)
- Данная программа создает новый класс "ElectricCar" с методом "charge" и атрибутом емкость батареи


4) Реализуйте инкапсуляцию для класса, созданного в первом задании. Создайте защищенный атрибут производителя и приватный атрибут модели. Вызовите защищенный атрибут и заставьте машину поехать. Напишите комментарии для кода, объясняющие его работу.
Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
class Car: #класс Car представляет автомобиль
    def __init__(self, make, model): #метод __init__ служит для инициализации объекта
        self._make = make #защищенный атрибут
        self.__model = model #приватный атрибут
    def drive(self): # метод drive описывает поведение автомобиля при вождении
        print(f"Driving the {self._make} {self.__model}") # вывод сообщения о том, какая машина управляется
my_car = Car("Toyota", "Corolla") #создание объекта my_car класса Car, передавая параметры "Toyota" и  "Corolla"
#эти значения будут присвоены свойствам make  и model объекта my_car
print(my_car._make) #доступ к защищённому атрибуту
my_car.drive() # вызов метода drive для объекта my_car
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pic8/pic4.png)
- Данная программа реализует инкапсуляцию для класса


5) Реализуйте полиморфизм создав основной (общий) класс "Shape", а также еще два класса "Rectangle” и “Circle”. Внутри последних двух классов реализуйте методы для подсчета площади фигуры. После этого создайте массив с фигурами, поместите туда круг и прямоугольник, затем при помощи цикла выведите их площади. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет листинг кода с комментариями и получившийся вывод в консоль.

```python
# Класс Shape является базовым классом для всех геометрических фигур.
class Shape:# Метод area() объявлен абстрактным методом, который будет переопределен в дочерних классах.
    def area(self):
        pass
# Класс Rectangle наследует от класса Shape и представляет прямоугольник.
class Rectangle(Shape):
    # Конструктор инициализирует ширину и высоту прямоугольника.
    def __init__(self, width, height):
        self.width = width
        self.height = height
    # Метод area() вычисляет площадь прямоугольника как произведение ширины на высоту.
    def area(self):
        return self.width * self.height
# Класс Circle наследует от класса Shape и представляет круг.
class Circle(Shape):
    # Конструктор инициализирует радиус круга.
    def __init__(self, radius):
        self.radius = radius
    # Метод area() вычисляет площадь круга по формуле 
    def area(self):
        return 3.14 * self.radius ** 2
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pic8/pic5.png)
- Данная программа реализует полиморфизм создав основной (общий) класс "Shape", а также еще два класса "Rectangle” и “Circle”

Самостоятельные задания:

1) Самостоятельно создайте класс и его объект. Они должны
отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Book:
    def __init__(self, title, author, pages):
        self.title = title
        self.author = author
        self.pages = pages
    def book_info(self):
        print(f'Название книги: {self.title}')
        print(f'Автор: {self.author}')
        print(f'Количество страниц: {self.pages}')
book1 = Book('Война и мир', 'Лев Толстой', 1225)
book1.book_info()
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pic8/pic6.png)
- Данная программа создает класс и его объект
2) Самостоятельно создайте атрибуты и методы для ранее созданного класса. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Book:
    def __init__(self, title, author, pages, genre=None, publisher=None):
        self.title = title
        self.author = author
        self.pages = pages
        self.genre = genre
        self.publisher = publisher
        self.current_page = 0
    def book_info(self):
        print(f'Название книги: {self.title}')
        print(f'Автор: {self.author}')
        print(f'Количество страниц: {self.pages}')
        print(f'Текущая страница: {self.current_page}')
        print(f'Жанр: {self.genre}')
        print(f'Издатель: {self.publisher}')
    def reset_current_page(self):
        self.current_page = 0
        print('Вы снова на первой странице.')
book1 = Book('Война и мир', 'Лев Толстой', 1225, 'Роман-эпопея', 'Русский вестник')
book1.book_info()
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pic8/pic7.png)
- Данная программа создает атрибуты и методы для ранее созданного класса 

3) Самостоятельно реализуйте наследование, продолжая работать с ранее созданным классом. Оно должно отличаться, от того, что указано в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Book:
    def __init__(self, title, author, pages, genre=None, publisher=None):
        self.title = title
        self.author = author
        self.pages = pages
        self.genre = genre
        self.publisher = publisher
        self.current_page = 0
    def book_info(self):
        print(f'Название книги: {self.title}')
        print(f'Автор: {self.author}')
        print(f'Количество страниц: {self.pages}')
        print(f'Текущая страница: {self.current_page}')
        print(f'Жанр: {self.genre}')
        print(f'Издатель: {self.publisher}')
    def reset_current_page(self):
        self.current_page = 0
        print('Вы снова на первой странице.')
book1 = Book('Война и мир', 'Лев Толстой', 1225, 'Роман-эпопея', 'Русский вестник')
book1.book_info()

class EBook(Book):
    def __init__(self, title, author, pages, file_format, genre=None, publisher=None):
        super().__init__(title, author, pages, genre, publisher)
        self.file_format = file_format
    def ebook_info(self):
        super().book_info()
        print(f'Формат файла: {self.file_format}')
ebook1 = EBook('1984', 'Джордж Оруэлл', 328, 'PDF', 'Антиутопия', 'Penguin Books')
ebook1.ebook_info()
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pic8/pic8.png)
- Данная программа реализует наследование

4) Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом. Она должна отличаться, от того, что указана в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.
```python
class Book:
    def __init__(self, title, author, pages, genre=None, publisher=None):
        self._title = title
        self._author = author
        self._pages = pages
        self._genre = genre
        self._publisher = publisher
        self._current_page = 0

    def book_info(self):
        print(f'Название книги: {self._title}')
        print(f'Автор: {self._author}')
        print(f'Количество страниц: {self._pages}')
        print(f'Текущая страница: {self._current_page}')
        print(f'Жанр: {self._genre}')
        print(f'Издатель: {self._publisher}')
    def reset_current_page(self):
        self._current_page = 0
        print('Вы снова на первой странице.')
    def title(self):
        return self._title
    def title(self, value):
        self._title = value
    def author(self):
        return self._author
    def author(self, value):
        self._author = value
    def pages(self):
        return self._pages
    def pages(self, value):
        if value > 0:
            self._pages = value
        else:
            raise ValueError("Количество страниц должно быть положительным числом.")
    def current_page(self):
        return self._current_page
    def current_page(self, value):
        if 0 <= value <= self._pages:
            self._current_page = value
        else:
            raise ValueError("Номер страницы должен быть в пределах от 0 до общего числа страниц.")
    def genre(self):
        return self._genre
    def genre(self, value):
        self._genre = value
    def publisher(self):
        return self._publisher
    def publisher(self, value):
        self._publisher = value
class EBook(Book):
    def __init__(self, title, author, pages, file_format, genre=None, publisher=None):
        super().__init__(title, author, pages, genre, publisher)
        self._file_format = file_format
    def ebook_info(self):
        super().book_info()
        print(f'Формат файла: {self._file_format}')
    def file_format(self):
        return self._file_format
    def file_format(self, value):
        self._file_format = value
book1 = Book('Война и мир', 'Лев Толстой', 1225, 'Роман-эпопея', 'Русский вестник')
book1.book_info()
ebook1 = EBook('1984', 'Джордж Оруэлл', 328, 'PDF', 'Антиутопия', 'Penguin Books')
ebook1.ebook_info()
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pic8/pic9.png)
-Данная программа реализует инкапсуляцию

5) Самостоятельно реализуйте полиморфизм. Он должен отличаться, от того, что указан в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.
```python
class Book:
    def __init__(self, title, author, pages, genre=None, publisher=None):
        self._title = title
        self._author = author
        self._pages = pages
        self._genre = genre
        self._publisher = publisher
        self._current_page = 0

    def display_info(self):
        print(f'Название книги: {self._title}')
        print(f'Автор: {self._author}')
        print(f'Количество страниц: {self._pages}')
        print(f'Текущая страница: {self._current_page}')
        print(f'Жанр: {self._genre}')
        print(f'Издатель: {self._publisher}')
    def reset_current_page(self):
        self._current_page = 0
        print('Вы снова на первой странице.')
    def title(self):
        return self._title
    def title(self, value):
        self._title = value
    def author(self):
        return self._author
    def author(self, value):
        self._author = value
    def pages(self):
        return self._pages
    def pages(self, value):
        if value > 0:
            self._pages = value
        else:
            raise ValueError("Количество страниц должно быть положительным числом.")
    def current_page(self):
        return self._current_page
    def current_page(self, value):
        if 0 <= value <= self._pages:
            self._current_page = value
        else:
            raise ValueError("Номер страницы должен быть в пределах от 0 до общего числа страниц.")
    def genre(self):
        return self._genre
    def genre(self, value):
        self._genre = value
    def publisher(self):
        return self._publisher
    def publisher(self, value):
        self._publisher = value
class EBook(Book):
    def __init__(self, title, author, pages, file_format, genre=None, publisher=None):
        super().__init__(title, author, pages, genre, publisher)
        self._file_format = file_format
    def display_info(self):
        super().display_info()
        print(f'Формат файла: {self._file_format}')
    def file_format(self):
        return self._file_format
    def file_format(self, value):
        self._file_format = value

def display_book_info(book):
    book.display_info()

book1 = Book('Война и мир', 'Лев Толстой', 1225, 'Роман-эпопея', 'Русский вестник')
ebook1 = EBook('1984', 'Джордж Оруэлл', 328, 'PDF', 'Антиутопия', 'Penguin Books')

display_book_info(book1)
display_book_info(ebook1)
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pic8/pic10.png)
- Данная программа реализует полиморфизм
