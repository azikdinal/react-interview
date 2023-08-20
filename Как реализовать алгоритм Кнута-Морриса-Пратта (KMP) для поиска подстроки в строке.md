Алгоритм Кнута-Морриса-Пратта (KMP) является эффективным алгоритмом для поиска подстроки в строке. Он работает на основе принципа сопоставления префиксов и суффиксов подстроки для определения наибольшего сдвига при несовпадении символов.

Процесс алгоритма Кнута-Морриса-Пратта для поиска подстроки в строке заключается в следующем:

1. Подготовка префикс-функции: Создаем префикс-функцию, которая будет хранить информацию о длине наибольшего собственного суффикса, который является префиксом подстроки. Это позволяет нам определить, насколько можно сдвинуться в строке, когда символы не совпадают.

2. Поиск подстроки: Используем префикс-функцию для сопоставления символов подстроки с символами строки. Если символы совпадают, продолжаем сравнивать следующие символы. Если символы не совпадают, используем префикс-функцию для определения сдвига и продолжаем поиск с новой позиции.

Пример реализации алгоритма Кнута-Морриса-Пратта для поиска подстроки в строке на языке JavaScript:

```javascript
function buildPrefixTable(pattern) {
  const prefixTable = [0]; // Префикс-таблица
  let prefixLength = 0; // Длина текущего префикса

  for (let i = 1; i < pattern.length; i++) {
    while (prefixLength > 0 && pattern[i] !== pattern[prefixLength]) {
      prefixLength = prefixTable[prefixLength - 1];
    }

    if (pattern[i] === pattern[prefixLength]) {
      prefixLength++;
    }

    prefixTable[i] = prefixLength;
  }

  return prefixTable;
}

function knuthMorrisPratt(text, pattern) {
  const prefixTable = buildPrefixTable(pattern);
  const indices = []; // Индексы совпадений

  let textIndex = 0; // Индекс в строке
  let patternIndex = 0; // Индекс в подстроке

  while (textIndex < text.length) {
    if (text[textIndex] === pattern[patternIndex]) {
      if (patternIndex === pattern.length - 1) {
        indices.push(textIndex - pattern.length + 1);
        patternIndex = prefixTable[patternIndex];
      } else {
        textIndex++;
        patternIndex++;
      }
    } else if (patternIndex > 0) {
      patternIndex = prefixTable[patternIndex - 1];
    } else {
      textIndex++;
    }
  }

  return indices;
}

// Пример использования:
const text = "ABABDABACDABABCABAB";
const pattern = "ABABCABAB";

const indices = knuthMorrisPratt(text, pattern);
console.log(indices); // Вывод: [10]
```

В данной реализации сначала создается префикс-таблица с помощью функции `buildPrefixTable`, которая определяет длины префиксов для каждого символа подстроки. Затем используется цикл `while` в функции `knuthMorrisPratt`, который выполняет поиск подстроки в строке. Если символы совпадают, индексы инкрементируются, и при полном совпадении подстроки добавляется индекс в массив `indices`. Если символы не совпадают, используется префикс-таблица для определения сдвига.
