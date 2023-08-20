Алгоритм поиска в ширину (Breadth-First Search, BFS) используется для обхода или поиска элемента в графе. Он проходит через все вершины графа на одном уровне перед переходом на следующий уровень.

Вот пример реализации алгоритма поиска в ширину в графе на языке JavaScript:

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

  bfs(startVertex) {
    const visited = {}; // Пометка посещенных вершин
    const queue = []; // Очередь для обхода

    visited[startVertex] = true;
    queue.push(startVertex);

    while (queue.length > 0) {
      const currentVertex = queue.shift();
      console.log(currentVertex); // Вывод текущей вершины

      const adjacentVertices = this.vertices[currentVertex];
      for (let i = 0; i < adjacentVertices.length; i++) {
        const adjacentVertex = adjacentVertices[i];
        if (!visited[adjacentVertex]) {
          visited[adjacentVertex] = true;
          queue.push(adjacentVertex);
        }
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

graph.bfs("A"); // Вывод: A, B, C, D, E
```

В данной реализации используется класс `Graph`, который представляет граф с помощью списка смежности. Метод `bfs` осуществляет обход графа в ширину. Он начинает с указанной стартовой вершины, помечает ее как посещенную, добавляет ее в очередь и затем поочередно извлекает вершины из очереди, помечая и добавляя их смежные вершины, если они еще не были посещены.

В результате вызова `graph.bfs("A")` будет выведена последовательность вершин A, B, C, D, E, соответствующая обходу графа в ширину.

Алгоритм поиска в ширину работает за время O(V + E), где V - количество вершин, E - количество ребер в графе. Он гарантирует нахождение кратчайшего пути от стартовой вершины ко всем достижимым вершинам.