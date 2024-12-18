# Расчётная работа
## Цели и задачи:

1. Составить алгоритм который ищет минимальное множество рёбернеориентированного графа,заданного матрицой инциндентности, удаление которых
позволяет сделать его деревом.
2. Перенести данный алгоритм на один из языков программирования (в данном случае Python 3.4)
3. Составить  отчёт и перенести его на удалённый репозиторий
## Основные понятия
### Граф

**Граф** — это математическая структура, состоящая из множества вершин (узлов) и множества рёбер (связей), которые соединяют пары вершин. Графы широко используются для моделирования различных систем, таких как сети, маршруты, социальные связи и многие другие.

**Пример**: Граф можно представить в виде набора городов (вершин), соединенных дорогами (рёбрами).

### Пример графа

В этом графе:
- Вершины: A, B, C, D
- Рёбра: (A-B), (A-C), (B-C), (B-D), (C-D)

### Дерево

**Дерево** — это частный случай графа, который является связным и ацикличным. Это означает, что дерево соединяет все свои вершины без циклов, и существует единственный путь между любой парой вершин.

**Пример**: Семейное древо, где узлы представляют членов семьи, а рёбра — родственные связи.

### Пример дерева

В этом дереве:
- Вершины: A, B, C, D, E
- Рёбра: (A-B), (A-C), (B-D), (B-E)

### Ориентированный граф

**Ориентированный граф** — это граф, в котором каждое ребро имеет направление. Это означает, что рёбра соединяют вершины в определенном порядке, что позволяет моделировать однонаправленные связи или потоки.

**Пример**: Сеть дорог с односторонним движением, где направление каждого ребра указывает допустимое направление движения.

### Пример ориентированного графа

В этом ориентированном графе:
- Вершины: A, B, C, D
- Рёбра: (A→B), (B→D), (D→C), (C→A)

### Неориентированный граф

**Неориентированный граф** — это граф, в котором все рёбра не имеют направления. Это означает, что связь между двумя вершинами симметрична, и рёбра могут быть пройдены в обоих направлениях. Неориентированные графы часто используются для моделирования симметричных отношений, таких как дружба в социальных сетях или физические пути между узлами в сетях.

**Пример**: Сеть дорог между городами, где каждая дорога может быть использована для движения в обоих направлениях.

### Пример неориентированного графа

В этом графе:
- Вершины: A, B, C, D
- Рёбра: (A-B), (A-C), (B-C), (B-D), (C-D)

Все рёбра могут быть пройдены в обоих направлениях, например, из A в B и из B в A.


### Минимальное остовное дерево

**Минимальное остовное дерево (MST)** — это остовное дерево графа, у которого сумма весов всех рёбер минимальна. Оно соединяет все вершины графа, используя наименьшее возможное суммарное количество рёбер, без образования циклов.

**Пример**: Оптимизированная система прокладки кабелей между компьютерами в сети, где минимизируется общая длина кабелей.

### Пример минимального остовного дерева

В этом минимальном остовном дереве:
- Вершины: A, B, C, D
- Рёбра: (A-B), (B-C), (B-D)
- Суммарный вес рёбер: 1 + 2 + 3 = 6

### Матрица инцидентности

**Матрица инцидентности** — это таблица, используемая в теории графов для представления связей между вершинами и рёбрами графа. В матрице инцидентности строки представляют вершины, а столбцы представляют рёбра. Элементы матрицы указывают на наличие связи (инцидентности) между вершинами и рёбрами.

- Если вершина инцидентна ребру (т.е. соединена этим ребром), то соответствующий элемент матрицы равен `1`.
- Если вершина не инцидентна ребру, то соответствующий элемент матрицы равен `0`.

### Пример матрицы инцидентности

Рассмотрим неориентированный граф с вершинами A, B, C и рёбрами e1, e2, e3.
Для этого графа матрица инцидентности будет выглядеть следующим образом:

|     | e1 | e2 | e3 |
|-----|----|----|----|
| **A** |  1 |  1 |  0 |
| **B** |  1 |  0 |  1 |
| **C** |  0 |  1 |  1 |

- Вершина A инцидентна рёбрам e1 и e2.
- Вершина B инцидентна рёбру e1 и e3.
- Вершина C инцидентна рёбру e2 и e3.

### Применение

Матрицы инцидентности широко используются в:
- **Анализе графов**: Для исследования структуры и свойств графов.
- **Алгоритмах на графах**: Для эффективного выполнения различных алгоритмов, таких как поиск минимального остовного дерева или поиск кратчайших путей.
- **Моделировании сетей**: Для представления сетей, таких как социальные сети, транспортные системы или электрические сети.

Матрица инцидентности является мощным инструментом для представления и анализа графов, обеспечивая ясное и наглядное отображение связей между вершинами и рёбрами.

### Вес ребра

**Вес ребра** — это значение, ассоциированное с ребром в графе, которое отражает определенную характеристику связи между двумя вершинами. Вес ребра может представлять различные аспекты, такие как расстояние, стоимость, время или любое другое измеримое свойство.

### Применение

Вес рёбер широко используется в различных алгоритмах на графах, например:
- **Поиск кратчайшего пути**: Алгоритмы, такие как алгоритм Дейкстры, используют вес рёбер для нахождения кратчайшего пути между вершинами.
- **Минимальное остовное дерево (MST)**: Алгоритмы, такие как алгоритм Прима и алгоритм Краскала, используют вес рёбер для нахождения MST, минимизируя общую сумму весов рёбер.

### Пример таблицы весов рёбер

| Ребро | Вершина 1 | Вершина 2 | Вес |
|-------|-----------|-----------|-----|
| e1    | A         | B         | 5   |
| e2    | A         | C         | 10  |
| e3    | B         | C         | 8   |
| e4    | B         | D         | 7   |
| e5    | C         | D         | 6   |

### Преимущества использования весов рёбер

- **Точность**: Помогают моделировать реальные системы с различными характеристиками связи.
- **Оптимизация**: Позволяют находить оптимальные пути, минимизируя или максимизируя определенные параметры.
- **Анализ**: Облегчают анализ графов и выполнение различных алгоритмов на графах.

Вес рёбер является важным инструментом для представления и анализа связей в графах, обеспечивая точную модель для решения разнообразных задач.


## Алгоритм кода
### Алгоритм постороен по [алгоритму Краскала](https://ru.wikipedia.org/wiki/%D0%90%D0%BB%D0%B3%D0%BE%D1%80%D0%B8%D1%82%D0%BC_%D0%9A%D1%80%D0%B0%D1%81%D0%BA%D0%B0%D0%BB%D0%B0)

### Описание

Алгоритм Краскала используется для нахождения минимального остовного дерева (MST) в неориентированном графе. Он работает путем сортировки всех рёбер по весу и последовательного добавления рёбер в остовное дерево, избегая циклов, пока все вершины не будут соединены.

### Шаги алгоритма

1. **Инициализация**:
    - Создайте множество для хранения рёбер минимального остовного дерева (MST).
    - Создайте массив для представления каждого множества вершин (инициализация с каждой вершиной в своем множестве).

2. **Сортировка рёбер**:
    - Отсортируйте все рёбра графа по их весам в порядке возрастания.

3. **Обработка рёбер**:
    - Проходите по отсортированному списку рёбер.
    - Для каждого ребра проверьте, принадлежат ли вершины этого ребра разным множествам:
        - Если да, добавьте ребро в MST и объедините множества этих вершин.
        - Если нет, пропустите ребро, чтобы избежать цикла.

4. **Остановка**:
    - Продолжайте добавлять рёбра до тех пор, пока все вершины не будут соединены (MST будет содержать `n-1` рёбер, где `n` — количество вершин).


## Пример работы программы
<a href="https://ltdfoto.ru/image/mvyRoU"><img src="https://ltdfoto.ru/images/2024/12/08/630D6B17-F631-4CB6-AA2D-00525DC3DA72.png" alt="630D6B17-F631-4CB6-AA2D-00525DC3DA72.png" border="0" /></a>

### В данной программе матрица инцидентности задается пользователем в виде .txt-файла [пример такого файла](https://github.com/tgh561/RR/blob/main/matrix.txt)
1. Пользователь даёт программе путь к файлу с матрицой
2. Затем подает программе 2 числа - количество вершин графа и количество рёбер.
3. Программа обрабатывает файл с матрицей и записывает ребра и их вес в список и сортирует их по мере возрастания веса рёбер
4. Созддается 3 списка: список соеденённых вершин, спикок групп соеденённых вершин и список рёбер минимального остова - все списки изначально пустые
5. 2 основных цикла for проходятся по списку отсортированных рёбер и выполняют манипуляции с ними в соответствии с алгоритмом:
  
    ```python
    # Обработка рёбер и объединение вершин
    for r in sorted_edges:
        if r[1] not in connected or r[2] not in connected:
            if r[1] not in connected and r[2] not in connected:
                groups[r[1]] = [r[1], r[2]]
                groups[r[2]] = groups[r[1]]
            else:
                if not groups.get(r[1]):
                    groups[r[2]].append(r[1])
                    groups[r[1]] = groups[r[2]]
                else:
                    groups[r[1]].append(r[2])
                    groups[r[2]] = groups[r[1]]

        mst.append(r)
        connected.add(r[1])
        connected.add(r[2])
    
    # Объединение разрозненных групп, если они соединены ребром
    for r in sorted_edges:
        if r[2] not in groups[r[1]]:
            mst.append(r)
            gr1 = groups[r[1]]
            groups[r[1]] += groups[r[2]]
            groups[r[2]] += gr1
    ```

- **Начало цикла**:
    ```python
    for r in sorted_edges:
    ```
    - Цикл `for` проходит по всем рёбрам в отсортированном списке `sorted_edges`. Каждое ребро `r` представляет собой кортеж `(w, u, v)`, где `w` — вес ребра, а `u` и `v` — вершины, которые оно соединяет.

- **Проверка на наличие вершин в множестве `connected`**:
    ```python
    if r[1] not in connected or r[2] not in connected:
    ```
    - Условие проверяет, содержатся ли хотя бы одна из вершин `u` или `v` в множестве `connected`. Если хотя бы одна вершина отсутствует, ребро можно добавлять без образования цикла.

- **Обе вершины не соединены**:
    ```python
    if r[1] not in connected and r[2] not in connected:
        groups[r[1]] = [r[1], r[2]]
        groups[r[2]] = groups[r[1]]
    ```
    - Если обе вершины `u` и `v` не соединены с остальными, создается новая группа в словаре `groups` и обе вершины добавляются в эту группу. Обе вершины указывают на одну и ту же группу.

- **Одна из вершин соединена**:
    ```python
    else:
        if not groups.get(r[1]):
            groups[r[2]].append(r[1])
            groups[r[1]] = groups[r[2]]
        else:
            groups[r[1]].append(r[2])
            groups[r[2]] = groups[r[1]]
    ```
    - Если одна из вершин уже соединена с остальными:
        - Если в словаре `groups` нет первой вершины `u`, вторая вершина `v` добавляет её в свою группу.
        - Иначе вторая вершина `v` добавляется в группу первой вершины `u`.

- **Добавление ребра в минимальный остов и обновление множества `connected`**:
    ```python
    mst.append(r)
    connected.add(r[1])
    connected.add(r[2])
    ```
    - Добавляем ребро `r` в список минимального остовного дерева `mst`.
    - Обе вершины `u` и `v` добавляются в множество `connected`.

### Второй цикл

Этот цикл объединяет разрозненные группы вершин, если они соединены ребром. 

### Подробное объяснение

+ **Начало второго цикла**:
    ```python
    for r in sorted_edges:
    ```
    - Цикл снова проходит по отсортированному списку рёбер `sorted_edges`.

+ **Проверка на раздельные группы**:
    ```python
    if r[2] not in groups[r[1]]:
    ```
    - Проверка, принадлежат ли вершины `u` и `v` разным группам.

+ **Объединение групп**:
    ```python
    mst.append(r)
    gr1 = groups[r[1]]
    groups[r[1]] += groups[r[2]]
    groups[r[2]] += gr1
    ```
    - Добавление ребра `r` в минимальное остовное дерево `mst`.
    - Объединение групп вершин `u` и `v` в одну общую группу.

Этот процесс продолжается до тех пор, пока все рёбра не будут обработаны, и все группы вершин не будут объединены в одно минимальное остовное дерево.


6. Программа выводит в консоль сначала список всех рёбер, затем удалённые рёбра, а после - минимальное остовное дерево, сфoрмированное самой программой.

# Вывод

## Во время выполнения Расчётной Работы были выполнены все поставленные задачи:

* Были изучены новые термины и понятия,
* Сотавлен алгоритм по условию задачи из [индивидуального варианта №24](https://docs.google.com/spreadsheets/d/1HTp6ehfjZ-J7uujVQCQodTtJ-tUJQM5IDe3kxOtpCl8/edit?gid=321859418#gid=321859418)
* [Алгоритм](https://github.com/tgh561/RR/blob/main/%D0%9B%D0%B8%D1%81%D1%82%D0%B8%D0%BD%D0%B3%20%D0%BA%D0%BE%D0%B4%D0%B0) был перенесён на один из языков программирования (Python 3.12)
* Был составлен отчет в виде readme-файла на удалённом репозитории
