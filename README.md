**Задание 1: Основы работы с изображениями

**Обязательная часть задания:

Программа должна открывать и сохранять изображения в формате 24-bit BMP.

В программе должны быть реализованы следующие операции обработки изображений:

Отражение изображения по вертикали и по горизонтали

Поворот изображений по и против часовой стрелки на 90, 180 и 270 градусов

Фильтр Собеля

Медианная фильтрация с квадратным окном произвольного размера

Свёртка с фильтром Гаусса с произвольным выбором параметра — радиуса σ с гамма-коррекцией

Вычисление модуля градиента как корень из суммы квадратов свёрток с первой производной фильтра Гаусса по горизонтали и вертикали (без гамма-коррекции)

**Дополнительная часть задания

Поворот изображения на произвольный угол относительно центра изображения с использованием билинейной интерполяции для устранения эффекта ступенчатости при повороте изображений с резкими контурами

**Замечания и рекомендации

Возможная реализация медианного фильтра для цветных изображений: независимая обработка R, G и B каналов, либо выбор значения из окрестности, минимизирующего суммарное расстояние до остальных значений пикселей из окрестности.

При применении операций фильтрации необходима корректная обработка границ изображения за счёт использования любого из методов экстраполяции: чётного продолжения, нечётного продолжения, дублирования граничных пикселей.

Результаты некоторых операций обработки изображений, приводящих к появлению изображений с отрицательными значениями пикселей, например, фильтр Собеля, нужно визуализировать, добавляя к каждому пикселю значение 128 - серую подложку.
Формат параметров командной строки

Программа должна поддерживать запуск из командной строки со строго определённым форматом команд:

`%programname% (command) (parameters...) (input_image) (output_image)`

**Список команд:

`mirror {x|y}`	Отражение по горизонтали или по вертикали, в зависомсти от указанного параметра

`rotate {cw|ccw} (angle)`	Поворот по или против часовой стрелки на заданное количество градусов, например: rotate cw 90

`sobel {x|y}`	Фильтр Собеля, обнаруживающий горизонтальные или вертикальные контуры

`median (rad)`	Медианная фильтрация, параметр rad — целочисленный радиус фильтра, то есть размер фильтра — квадрат со стороной (2 * rad + 1)

`gauss (sigma) (gamma)`	Фильтр Гаусса, параметр sigma — вещественный параметр фильтра, gamma — значение гаммы

`gradient (sigma)`	Модуль градиента
