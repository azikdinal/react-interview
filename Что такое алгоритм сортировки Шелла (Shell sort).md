Алгоритм сортировки Шелла (Shell Sort) - это усовершенствованный алгоритм сортировки вставками, который основан на идее постепенного сортирования элементов с большими промежутками, а затем уменьшения промежутков до сортировки соседних элементов. Он получил свое название в честь Дональда Шелла, который разработал этот алгоритм в 1959 году.

Вот пример реализации алгоритма сортировки Шелла (Shell Sort) на языке JavaScript:

```javascript
function shellSort(arr) {
  const n = arr.length;
  let gap = Math.floor(n / 2); // Начальное значение промежутка

  while (gap > 0) {
    for (let i = gap; i < n; i++) {
      const temp = arr[i];
      let j = i;

      while (j >= gap && arr[j - gap] > temp) {
        arr[j] = arr[j - gap];
        j -= gap;
      }

      arr[j] = temp;
    }

    gap = Math.floor(gap / 2); // Уменьшаем промежуток
  }

  return arr;
}

// Пример использования:
const arr = [9, 4, 7, 2, 1, 5, 6];
const sortedArr = shellSort(arr);
console.log(sortedArr); // Вывод: [1, 2, 4, 5, 6, 7, 9]
```

В данной реализации алгоритма сортировки Шелла используется цикл, который последовательно уменьшает промежуток `gap` от начального значения до 1. Затем для каждого значения `gap` выполняется сортировка вставками для элементов, находящихся на расстоянии `gap` друг от друга. Внутренний цикл сортировки вставками проходит через элементы с шагом `gap` и сравнивает их с предыдущими элементами в промежутке `gap`. Если элементы находятся в неправильном порядке, они меняются местами. По мере прохождения циклов промежуток `gap` уменьшается, и процесс повторяется до тех пор, пока промежуток не станет равным 1.

Алгоритм сортировки Шелла имеет временную сложность, которая зависит от выбранной последовательности промежутков. Хорошие последовательности приводят к временной сложности O(n log n), но самая худшая последовательность может привести к временной сложности O(n^2). Однако на практике сортировка Шелла обычно выполняется быстрее, чем сортировка вставками, и хорошо работает на небольших и средних размерах массивов.