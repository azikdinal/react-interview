Алгоритм сортировки слиянием (Merge Sort) - это эффективный алгоритм сортировки, который использует подход "разделяй и властвуй". Он разбивает массив на две равные половины, рекурсивно сортирует эти половины, а затем объединяет их в отсортированный массив.

Вот пример реализации алгоритма сортировки слиянием с использованием рекурсии на языке JavaScript:

```javascript
function mergeSort(arr) {
  if (arr.length <= 1) {
    return arr; // Базовый случай: если массив пустой или содержит только один элемент, он уже отсортирован
  }

  const middle = Math.floor(arr.length / 2); // Находим середину массива
  const left = arr.slice(0, middle); // Делим массив на две половины
  const right = arr.slice(middle);

  // Рекурсивно сортируем каждую половину массива
  const sortedLeft = mergeSort(left);
  const sortedRight = mergeSort(right);

  // Объединяем две отсортированные половины в один отсортированный массив
  return merge(sortedLeft, sortedRight);
}

function merge(left, right) {
  let merged = [];
  let leftIndex = 0;
  let rightIndex = 0;

  // Объединяем элементы из left и right, сравнивая их
  while (leftIndex < left.length && rightIndex < right.length) {
    if (left[leftIndex] < right[rightIndex]) {
      merged.push(left[leftIndex]);
      leftIndex++;
    } else {
      merged.push(right[rightIndex]);
      rightIndex++;
    }
  }

  // Добавляем оставшиеся элементы из left и right
  while (leftIndex < left.length) {
    merged.push(left[leftIndex]);
    leftIndex++;
  }

  while (rightIndex < right.length) {
    merged.push(right[rightIndex]);
    rightIndex++;
  }

  return merged;
}

// Пример использования:
const arr = [9, 4, 7, 2, 1, 5, 6];
const sortedArr = mergeSort(arr);
console.log(sortedArr); // Вывод: [1, 2, 4, 5, 6, 7, 9]
```

В данной реализации функция `mergeSort` принимает массив и выполняет рекурсивное разделение и сортировку его половин. В базовом случае, когда массив пустой или содержит только один элемент, функция возвращает его. В противном случае, массив делится пополам, и каждая половина рекурсивно сортируется с помощью `mergeSort`. Затем отсортированные половины объединяются вместе с помощью функции `merge`, которая сравнивает элементы и формирует отсортированный массив.

Алгоритм сортировки слиянием имеет временную сложность O(n log n), где n - размер массива. Он стабильный и гарантирует сортировку в худшем случае, что делает его полезным для больших объемов данных.