# Задача 2. Фигуры. Стороны и углы
В этом задании мы усложним иерархию классов для усложнённой предметной области

Теперь у нас в появляется информация о длине сторон и углах наших фигур, а также несколько более конкретных фигур
Итак, теперь в треугольнике мы должны хранить информацию о длине всех его трёх сторон (`a`, `b`, `c`) и значениях его трёх углов (`A`, `B`, `C`)
В четырёхугольнике мы храним, соответственно, информацию о длине его четырёх сторон (`a`, `b`, `c`, `d`) и значениях его четырёх углов (`A`, `B`, `C`, `D`)

Также у нас появляются некоторые более конкретные фигуры: 
 - прямоугольный треугольник (угол `C` всегда равен 90)
 - равнобедренный треугольник (стороны `a` и `c` равны, углы `A` и `C` равны)
 - равносторонний треугольник (все стороны равны, все углы равны 60)
 - прямоугольник (стороны `a`,`c` и `b`,`d` попарно равны, все углы равны 90)
 - квадрат (все стороны равны, все углы равны 90)
 - параллелограмм (стороны `a`,`c` и `b`,`d` попарно равны, углы `A`,`C` и `B`,`D` попарно равны)
 - ромб (все стороны равны, углы `A`,`C` и `B`,`D` попарно равны)
 
Мы должны иметь возможность узнать у каждой фигуры длины её сторон и значения её углов, но извне мы не должны быть способны изменить длины сторон и углы

Не должно быть возможности создать фигуры, не удовлетворяющие вышеперечисленным условиям (например, нельзя создать квадрат с разными углами). Однако геометрические соотношения проверять не нужно (например, сумма углов в треугольнике может быть не равна 180)

Задача: спроектировать и реализовать классы, описывающие предметную область. Продемонстрировать их работу - создайте по одному экземпляру каждой фигуры и выведите на экран информацию о длинах её сторон и величине её углов (значения используйте произвольные)

Инициализацию длин сторон и величин углов необходимо выполнить с помощью вызова базовых конструкторов

### Пример работы программы
#### Консоль
```
Треугольник:
Стороны: a=10 b=20 c=30
Углы: A=50 B=60 C=70

Прямоугольный треугольник:
Стороны: a=10 b=20 c=30
Углы: A=50 B=60 C=90

Равнобедренный треугольник:
Стороны: a=10 b=20 c=10
Углы: A=50 B=60 C=50

Равносторонний треугольник:
Стороны: a=30 b=30 c=30
Углы: A=60 B=60 C=60

Четырёхугольник:
Стороны: a=10 b=20 c=30 d=40
Углы: A=50 B=60 C=70 D=80

Прямоугольник:
Стороны: a=10 b=20 c=10 d=20
Углы: A=90 B=90 C=90 D=90

Квадрат:
Стороны: a=20 b=20 c=20 d=20
Углы: A=90 B=90 C=90 D=90

Параллелограмм:
Стороны: a=20 b=30 c=20 d=30
Углы: A=30 B=40 C=30 D=40

Ромб:
Стороны: a=30 b=30 c=30 d=30
Углы: A=30 B=40 C=30 D=40
```
#### Подсказки

> Не читайте этот раздел сразу, попытайтесь сначала решить задачу самостоятельно :)

<details>

<summary>Подсказка. Что использовать для решения?</summary>

Нам нужно будет создать класс для каждой фигуры

Иерархия наследования для более конкретных фигур может различаться - например, параллелограмм будет наследоваться от четырёхугольника, прямоугольник и ромб - от параллелограмма. Квадрат было бы логично унаследовать от ромба и прямоугольника - ведь он является и тем, и другим - но мы помним, что стоит избегать множественного наследования, поэтому унаследуем его либо от прямоугольника, либо от ромба (по желанию)

Для хранения информации о длинах сторон и величинах углов создадим поля `a`, `b`, `c` и  `A`, `B`, `C` в классе треугольника и соответствующие им `get_` методы, а в классе четырёхугольника создадим поля `a`, `b`, `c`, `d` и  `A`, `B`, `C`, `D` и соответствующие им `get_` методы

У нас появятся разные конструкторы - например, у конструктора класса треугольника  будет 6 параметров - три для длин сторон, три для углов. А у конструктора класса прямоугольного треугольника будет 5 параметров - угол `C` у него всегда равен 90. У класса равностороннего треугольника конструктор будет принимать только один параметр - это длина его сторон

</details>