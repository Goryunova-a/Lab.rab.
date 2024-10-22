# Тема 7. Работа с файлами (ввод, вывод)
Отчет по Теме #7 выполнила:
- Горюнова Алина Алексеевна
- ИВТ-22-1

| Задание | Лаб_раб | Сам_раб|
| ------ | ------ | ------|
| Задание 1 | + | + |
| Задание 2 | + | + |
| Задание 3 | + | + |
| Задание 4 | + | + |
| Задание 5 | + | + |
| Задание 6 | + |
| Задание 7 | + |
| Задание 8 | + |
| Задание 9 | + |
| Задание 10 | + |


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.


Лабораторные задания:	
1) Составьте текстовый файл и положите его в одну директорию с программой на Python. Текстовый файл должен состоять минимум из двух строк.

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic1.png)
- Создание текстового файла


2) Напишите программу, которая выведет только первую строку из вашего файла, при этом используйте конструкцию open()/close().

```python
f = open('input.txt', 'r')
print(f.readline())
f.close()
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic2.png)
- Данная программа выведет только первую строку из вашего файла, при этом используйте конструкцию open()/close()


3) Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию open()/close().

```python
f = open('input.txt', 'r')
print(f.readlines())
f.close()
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic3.png)
- Данная программа выведет все строки из файла в массиве, при этом используя конструкцию open()/close()


4) Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию with open().

```python
with open('input.txt') as f:
    print(f.readlines())
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic4.png)
- Данная программа выведет все строки из файла в массиве, при этом используя конструкцию with open()


5) Напишите программу, которая выведет каждую строку из вашего файла отдельно, при этом используйте конструкцию with open().

```python
with open('input.txt') as f:
    for line in f:
        print(line)
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic5.png)
- Данная программа выведет каждую строку из файла отдельно, при этом используя конструкцию with open()

6) Напишите программу, которая будет добавлять новую строку в ваш файл, а потом выведет полученный файл в консоль. Вывод можно осуществлять любым способом. Обязательно проверьте сам файл, чтобы изменения в нем тоже отображались.

```python
with open('input.txt', 'a+') as f:
    f.write('\nIm additional line')

with open('input.txt', 'r') as f:
    result = f.readlines()
    print(result)
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic6.png)
- Данная программа добавляет новую строку в файл, а потом выводит полученный файл в консоль


7) Напишите программу, которая перепишет всю информацию, которая была у вас в файле до этого, например напишет любые данные из произвольно вами составленного списка. Также не забудьте проверить что измененная вами информация сохранилась в файле.

```python
lines = ['one', 'two','three']
with open('input.txt', 'w') as f:
    for line in lines:
        f.write('\nCycle run ' + line)
    print('Done!')
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic7.png)
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic7_1.png)
- Данная программа переписывает всю информацию, которая была у в файле до этого


8) Выберите любую папку на своем компьютере, имеющую вложенные директории. Выведите на печать в терминал ее содержимое, как и всех подкаталогов при помощи функции print_docs(directory).

```print
import os
def print_docs(directory):
    all_files = os.walk(directory)
    for catalog in all_files:
        print(f'Папка {catalog[0]} сщдержит: ')
    print(f'Директории: {", ".join([folder for folder in catalog[1]])}')
    print(f'Файлы: {", ".join([file for file in catalog[2]])}')
    print('-' * 40)
print_docs('/Users/Alina/Documents/универ/программная инженерия/pics7')
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic8.png)
- Данная программа выводит на печать в терминал ее содержимое любой папки на устройстве, как и всех подкаталогов при помощи функции print_docs(directory).


9) Документ «input.txt» содержит следующий текст:
Приветствие
Спасибо
Извините
Пожалуйста
До свидания
Ты готов?
Как дела?
С днем рождения!
Удача!
Я тебя люблю.
анов
Требуется реализовать функцию, которая выводит слово, имеющее максимальную длину (или список слов, если таковых несколько). Проверьте работоспособность программы на своем наборе данных


доброе утро
здравствуйте
добрый вечер
всего хорошего
до новых встреч
так держать 
у тебя всё получится
не сдавайся
ты молодец

```python
def longest_words(file):
    with open(file, encoding='utf-8') as f:
        words = f.read().split()
        max_length = len(max(words, key=len))
        for word in words:
            if  len(word) == max_length:
                sought_words = word
        if len(sought_words) ==1:
            return sought_words[0]
        return sought_words
print(longest_words('input.txt'))
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic9.png)
- Данная программа реализовывает функцию, которая выводит слово, имеющее максимальную длину


10)
Требуется создать csv-файл «rows_300.csv» со следующими столбцами:
• No - номер по порядку (от 1 до 300);
• Секунда – текущая секунда на вашем ПК;
• Микросекунда – текущая миллисекунда на часах.
Для наглядности на каждой итерации цикла искусственно приостанавливайте скрипт на 0,01 секунды.

```python
import csv
import datetime
import time
with open('rows_300.csv', 'w', encoding='utf-8', newline='') as f:
    writer = csv.writer(f)
    writer.writerow(['№', 'Cекунда ', 'Микросекунда'])
    for line in range(1,301):
        writer.writerow([line, datetime.datetime.now().second,
                         datetime.datetime.now().microsecond])
        time.sleep(0.01)
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic10.png)
- Данная программа создает csv-файл «rows_300.csv» со следующими столбцами:
• No - номер по порядку (от 1 до 300);
• Секунда – текущая секунда на вашем ПК;
• Микросекунда – текущая миллисекунда на часах.


Самостоятельные задания:

1) Найдите в интернете любую статью (объем статьи не менее 200 слов), скопируйте ее содержимое в файл и напишите программу, которая считает количество слов в текстовом файле и определит самое часто встречающееся слово. Результатом выполнения задачи будет: скриншот файла со статьей, листинг кода, и вывод в консоль, в котором будет указана вся необходимая информация.

```python

import os
from collections import Counter
def count_words(filename):
    with open(filename, encoding='utf8') as f:
        content = f.read()  
    words = content.split()
    return len(words), Counter(words).most_common(1)[0][0]
if __name__ == "__main__":
    input_file = 'input.txt'
    total_words, most_common_word = count_words(input_file)   
    print(f"Количество слов в файле: {total_words}")
    print(f"Самое частое слово: {most_common_word}")
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic11.png)
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic11_1.png)
- Данная программа  считает количество слов в текстовом файле и определяет самое часто встречающееся слово.


2) У вас появилась потребность в ведении книги расходов, посмотрев все существующие варианты вы пришли к выводу что вас ничего не устраивает и нужно все делать самому. Напишите программу для учета расходов. Программа должна позволять вводить информацию о расходах, сохранять ее в файл и выводить существующие данные в консоль. Ввод информации происходит через консоль. Результатом выполнения задачи будет: скриншот файла с учетом расходов, листинг кода, и вывод в консоль, с демонстрацией
работоспособности программы.

```python
def main():
    data = []
    
    while True:
        operation = input("Введите операцию (ввод, добавить, вывести, выйти): ")
        if operation == 'ввод':
            amount = float(input("Введите сумму расходов: "))
            date = input("Введите дату (ДД-ММ-ГГГГ): ")
            description = input("Введите описание: ")
            
            expense = {"amount": amount, "date": date, "description": description}
            data.append(expense)
            print("Расход добавлен.")
        elif operation == 'добавить':
            continue
        elif operation == 'вывести':
            for item in data:
                print(f"Сумма: {item['amount']}, Дата: {item['date']}, Описание: {item['description']}")
        elif operation == 'выйти':
            break
        else:
            print("Неверная команда")

    save_data_to_file(data)

def save_data_to_file(data):
    with open('expenses.json', 'w') as outfile:
        json.dump(data, outfile)

def load_data_from_file():
    try:
        with open('expenses.json', 'r') as infile:
            return json.load(infile)
    except FileNotFoundError:
        return []

if __name__ == "__main__":
    main()
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic12.png)
- Данная программа позволяет вводить информацию о расходах, сохранять ее в файл и выводить существующие данные в консоль


3) Имеется файл input.txt с текстом на латинице. Напишите программу, которая выводит следующую статистику по тексту: количество букв латинского алфавита; число слов; число строк.
• Текст в файле: Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex. Complex is better than complicated. Ожидаемый результат:
Input file contains:
108 letters
20 words
4 lines

```python
def calculate_statistics(filename):
    with open(filename, 'r', encoding='utf-8') as file:
        text = file.read().lower()
    latin_letters = sum(1 for c in text if c.isalpha() and c.isascii())
    words = text.split()
    number_of_words = len(words)
    lines = text.split('\n')
    number_of_lines = len(lines)
    statistics = {
        'latin_letters': latin_letters,
        'number_of_words': number_of_words,
        'number_of_lines': number_of_lines}
    return statistics
filename = 'input.txt'
statistics = calculate_statistics(filename)

for key, value in statistics.items():
    print(f"{key}: {value}")
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic13.png)
- Данная программа выводит следующую статистику по тексту: количество букв латинского алфавита; число слов; число строк.


4) Напишите программу, которая получает на вход предложение, выводит его в терминал, заменяя все запрещенные слова звездочками * (количество звездочек равно количеству букв в слове). Запрещенные слова, разделенные символом пробела, хранятся в текстовом файле input.txt. Все слова в этом файле записаны в нижнем регистре. Программа должна заменить запрещенные слова, где бы они ни встречались, даже в середине другого слова. Замена производится независимо от регистра: если
файл input.txt содержит запрещенное слово ехаm, то слова ехат, Exam, ЕхаM, EXAM и exAm должны быть заменены на ****.
Запрещенные слова:
hello email python the exam wor is
• Предложение для проверки:
Hello, world! Python IS the programming language of the future. My EMAIL is....
PYTHON is awesome!!!!
• Ожидаемый результат:
*****
*** ***ld! ****** ***** programming language of *** future. My
*******
****** ** awesome!!!!

```python
def mask_words(sentence, forbidden_words):
    sentence = sentence.lower()
    for word in forbidden_words:
        sentence = sentence.replace(word, ('*' * len(word)))
    return sentence
def main():
    with open('input.txt', 'r') as f:
        forbidden_words = f.read().strip().split()
    test_sentence = "Hello, world! Python IS the programming language of the future. My EMAIL is.... PYTHON is awesome!!!!".lower()
    modified_sentence = mask_words(test_sentence, forbidden_words)
    print(modified_sentence)
if __name__ == "__main__":
    main()
```

![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic14.png)
- Данная программа получает на вход предложение, выводит его в терминал, заменяя все запрещенные слова звездочками *. Программа заменяет запрещенные слова, где бы они ни встречались, даже в середине другого слова.


5) Самостоятельно придумайте и решите задачу, которая будет взаимодействовать с текстовым файлом.

Напишите программу, которая будет читать текстовый файл, удалять все пустые строки и сохранять результат в новом файле.

```python
def remove_empty_lines(path_to_input_file, path_to_output_file):
    with open(path_to_input_file, 'r') as input_file:
        with open(path_to_output_file, 'w') as output_file:
            for line in input_file:
                if line.strip():
                    output_file.write(line)

if __name__ == "__main__":
    input_file_path = 'input.txt'
    output_file_path = 'output.txt'
    remove_empty_lines(input_file_path, output_file_path)
    print(f"Результат сохранен в файле {output_file_path}.")
```
![Меню](https://github.com/Goryunova-a/Lab.rab./blob/main/pics7/pic15.png)
- Данная программа читает текстовый файл, удаляет все пустые строки и сохраняет результат в новом файле.
