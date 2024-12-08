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

**Ориентированный граф (диграф)** — это граф, в котором каждое ребро имеет направление. Это означает, что рёбра соединяют вершины в определенном порядке, что позволяет моделировать однонаправленные связи или потоки.

**Пример**: Сеть дорог с односторонним движением, где направление каждого ребра указывает допустимое направление движения.

### Пример ориентированного графа

В этом дереве:
- Вершины: A, B, C, D, E
- Рёбра: (A-B), (A-C), (B-D), (B-E)

### Ориентированный граф

**Ориентированный граф (диграф)** — это граф, в котором каждое ребро имеет направление. Это означает, что рёбра соединяют вершины в определенном порядке, что позволяет моделировать однонаправленные связи или потоки.

**Пример**: Сеть дорог с односторонним движением, где направление каждого ребра указывает допустимое направление движения.

### Пример ориентированного графа

В этом минимальном остовном дереве:
- Вершины: A, B, C, D
- Рёбра: (A-B), (B-C), (B-D)
- Суммарный вес рёбер: 1 + 2 + 3 = 6

# Алгоритм кода
