В TypeScript можно добавить типы для функций, принимающих переменное количество аргументов, с помощью синтаксиса `rest parameters` и указания типа для каждого аргумента. Rest parameters позволяют указывать, что функция может принимать переменное количество аргументов и объединять их в массив.

Вот примеры:

1. Использование `rest parameters` с типом `Array`:
```typescript
function sumNumbers(...numbers: number[]): number {
  return numbers.reduce((sum, num) => sum + num, 0);
}

const result = sumNumbers(1, 2, 3, 4, 5);
console.log(result); // 15
```
В этом примере функция `sumNumbers` принимает переменное количество числовых аргументов и возвращает их сумму. Мы используем синтаксис `...numbers: number[]`, чтобы объявить `rest parameter` с типом `number[]`, что означает, что аргументы должны быть числами. 

2. Использование `rest parameters` с типом кортежа:
```typescript
type Point = [number, number];

function printPoints(...points: Point[]): void {
  points.forEach(point => {
    console.log(`x: ${point[0]}, y: ${point[1]}`);
  });
}

printPoints([1, 2], [3, 4], [5, 6]);
```
В этом примере функция `printPoints` принимает переменное количество аргументов типа `Point`, где `Point` представляет собой кортеж из двух чисел. Мы используем `rest parameter` с типом `Point[]`, чтобы указать, что аргументы должны быть кортежами из двух чисел.

3. Указание типа для каждого аргумента:
```typescript
function concatenateStrings(...strings: string[]): string {
  return strings.join('');
}

const result = concatenateStrings('Hello', ' ', 'TypeScript');
console.log(result); // "Hello TypeScript"
```
В этом примере функция `concatenateStrings` принимает переменное количество аргументов типа `string` и объединяет их в одну строку с помощью метода `join`. Мы не указываем тип `rest parameter`, но каждый аргумент является типом `string`.

Таким образом, вы можете добавлять типы для функций, принимающих переменное количество аргументов, с использованием `rest parameters` и указания соответствующих типов. Это позволяет TypeScript проводить статическую проверку типов и обеспечивать корректное использование функций с переменным числом аргументов.