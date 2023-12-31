Алгоритм сортировки пузырьком (Bubble Sort) - это простой алгоритм сортировки, который путем последовательного сравнения и обмена соседних элементов постепенно перемещает наибольшие элементы в конец массива. По мере прохождения по массиву на каждой итерации наибольший элемент "всплывает" на свою правильную позицию, а остальные элементы сдвигаются влево.

Вот пример реализации алгоритма сортировки пузырьком (Bubble Sort) на языке JavaScript:

```javascript
function bubbleSort(arr) {
  const n = arr.length;

  for (let i = 0; i < n - 1; i++) {
    let swapped = false;

    // Перебираем элементы массива
    for (let j = 0; j < n - i - 1; j++) {
      // Сравниваем соседние элементы и меняем их местами, если нужно
      if (arr[j] > arr[j + 1]) {
        swap(arr, j, j + 1);
        swapped = true;
      }
    }

    // Если на текущей итерации не было обменов, массив уже отсортирован
    if (!swapped) {
      break;
    }
  }

  return arr;
}

// Функция для обмена элементов массива
function swap(arr, i, j) {
  const temp = arr[i];
  arr[i] = arr[j];
  arr[j] = temp;
}

// Пример использования:
const arr = [9, 4, 7, 2, 1, 5, 6];
const sortedArr = bubbleSort(arr);
console.log(sortedArr); // Вывод: [1, 2, 4, 5, 6, 7, 9]
```

В данной реализации алгоритма сортировки пузырьком используется два цикла. Внешний цикл выполняется n - 1 раз, где n - количество элементов в массиве. Внутренний цикл проходит по неотсортированной части массива и сравнивает соседние элементы. Если текущий элемент больше следующего элемента, они меняются местами. Таким образом, на каждой итерации наибольший элемент "всплывает" на свою правильную позицию в конце массива.

Алгоритм сортировки пузырьком имеет временную сложность O(n^2) в худшем и среднем случае, где n - количество элементов в массиве. Он является устойчивым алгоритмом сортировки, то есть сохраняет относительный порядок равных элементов. Алгоритм сортировки пузырьком не является эффективным для больших массивов, но может быть полезным для сортировки небольших или почти отсортированных массивов.