# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Ямбушев Артём Дамирович
- РИ210933
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Ознакомиться с основными операторами зыка Python на примере реализации линейной регрессии.

## Задание 1
### Написать программы Hello World на Python и Unity
Ход работы:
- Написал и запустил файл .py в PyCharm:
![image](https://user-images.githubusercontent.com/101344196/192602782-092a45da-0ffb-450a-90ae-5eb3875c7796.png)

- После объединения Unity и VS Code написал код и запустил в 3D-проекте Unity. Результат работы в консоли:
![image](https://user-images.githubusercontent.com/101344196/192607206-350a16e2-18e4-4c35-83c7-3f92ba8c54ac.png)

## Задание 2
Ход работы:
- Произвёл подготовку данных для работы с алгоритмом линейной регрессии используя Anaconda и Yupiter.

```py

In [ ]:
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline

x = [3, 21, 22, 34, 54, 34, 55, 67, 89, 99]
x = np.array(x)
y = [2, 22, 24, 65, 79, 82, 55, 130, 150, 199]
y = np.array(y)

plt.scatter(x,y)

```
- Вывод после подготовки данных:
![image](https://user-images.githubusercontent.com/101344196/192848677-4fc7e091-c144-49dd-82ed-4cf397afbce1.png)

- Далее определил связанные функции, а именно: Функцию модели, Функцию потерь, Функцию оптимизации.
```py

import numpy as np
import matplotlib.pyplot as plt
 
x = [3, 21, 22, 34, 54, 34, 55, 67, 89, 99]
x = np.array(x)
y = [2, 22, 24, 65, 79, 82, 55, 130, 150, 199]
y = np.array(y)
 
plt.scatter(x, y)
 
def model(a, b, x):
    return a * x + b
  
def loss_function(a, b, x, y):
    num = len(x)
    prediction = model(a, b, x)
    return (0.5 / num) * (np.square(prediction - y)).sum()
  
def optimize(a, b, x, y):
    num = len(x)
    prediction = model(a, b, x)
    da = (1.0 / num) * ((prediction - y) * x).sum()
    db = (1.0 / num) * ((prediction - y).sum())
    a = a - Lr * da
    b = b - Lr * db
    return a, b
 
def iterate(a, b, x, y, times):
    for i in range(times):
        a, b = optimize(a, b, x, y)
    return a, b
 
a = np.random.rand(1)
b = np.random.rand(1)
Lr = 0.000001
 
a, b = iterate(a, b, x, y, 1000)
prediction = model(a, b, x)
loss = loss_function(a, b, x, y)
print(a, b, loss)
plt.scatter(x, y)
plt.plot(x, prediction)

```
- результат работы финальной версии теста:
![image](https://user-images.githubusercontent.com/101344196/192851443-969f36f8-f147-4775-be26-6b8d62cf5ddb.png)

- После начал производить итерации

- Результат первой итерации
![image](https://user-images.githubusercontent.com/101344196/192858593-5d7b4855-162a-4665-8095-92ca2bd3a482.png)

- Результат второй итерации
- ![image](https://user-images.githubusercontent.com/101344196/192859109-30f7a15b-19ae-4efa-a8a3-3ba3140eeeb8.png)

- Результат третей итерации
- ![image](https://user-images.githubusercontent.com/101344196/192859665-6a0ed342-2892-41c6-b2dd-856464d3d9a7.png)

- Результат четвёртой итерации
- ![image](https://user-images.githubusercontent.com/101344196/192859874-9a6fec80-0aa3-4471-9c94-5ef28b843aaf.png)

- Результат пятой итерации
- ![image](https://user-images.githubusercontent.com/101344196/192860016-ade4d20c-0f19-469c-99f9-470011259e0a.png)

- Результат 10000 операции
- ![image](https://user-images.githubusercontent.com/101344196/192860179-15934d86-6d82-4662-98cc-3a8799cf7ae8.png)

## Выводы

Абзац умных слов о том, что было сделано и что было узнано.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
