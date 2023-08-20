Алгоритм поиска в глубину (Depth-First Search, DFS) используется для обхода или поиска элемента в графе. Он идет "вглубь" графа, посещая все возможные вершины перед переходом к следующей непосещенной вершине.

Вот пример реализации алгоритма поиска в глубину в графе на языке JavaScript:

```javascript
// Реализация графа с использованием списка смежности
class Graph {
  constructor() {
    this.vertices = {}; // Список смежности
  }

  addVertex(vertex) {
    this.vertices[vertex] = [];
  }

  addEdge(vertex1, vertex2) {
    this.vertices[vertex1].push(vertex2);
    this.vertices[vertex2].push(vertex1);
  }

  dfs(startVertex) {
    const visited = {}; // Пометка посещенных вершин

    this.dfsRecursive(startVertex, visited);
  }

  dfsRecursive(vertex, visited) {
    visited[vertex] = true;
    console.log(vertex); // Вывод текущей вершины

    const adjacentVertices = this.vertices[vertex];
    for (let i = 0; i < adjacentVertices.length; i++) {
      const adjacentVertex = adjacentVertices[i];
      if (!visited[adjacentVertex]) {
        this.dfsRecursive(adjacentVertex, visited);
      }
    }
  }
}

// Пример использования:
const graph = new Graph();
graph.addVertex("A");
graph.addVertex("B");
graph.addVertex("C");
graph.addVertex("D");
graph.addVertex("E");

graph.addEdge("A", "B");
graph.addEdge("A", "C");
graph.addEdge("B", "D");
graph.addEdge("C", "E");

graph.dfs("A"); // Вывод: A, B, D, C, E
```

В данной реализации используется класс `Graph`, который представляет граф с помощью списка смежности. Метод `dfs` осуществляет обход графа в глубину. Он начинает с указанной стартовой вершины, помечает ее как посещенную, выводит ее значение и рекурсивно вызывает себя для каждой непосещенной смежной вершины.

В результате вызова `graph.dfs("A")` будет выведена последовательность вершин A, B, D, C, E, соответствующая обходу графа в глубину.

Алгоритм поиска в глубину работает за время O(V + E), где V - количество вершин, E - количество ребер в графе. Он обычно реализуется с помощью рекурсии и использует стек для сохранения порядка посещения вершин. Алгоритм поиска в глубину может быть полезен при задачах, связанных с обходом графа и поиску путей между вершинами.