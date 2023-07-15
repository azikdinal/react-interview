В TypeScript декомпозиция типов, или type deconstruction, относится к процессу извлечения или разбора отдельных частей типа или интерфейса. Это позволяет получить доступ к отдельным свойствам или типам внутри более сложных типов данных.

Вот несколько примеров декомпозиции типов в TypeScript:

1. Декомпозиция объекта:
```typescript
interface Person {
  name: string;
  age: number;
  address: {
    city: string;
    country: string;
  };
}

const person: Person = {
  name: "John",
  age: 30,
  address: {
    city: "New York",
    country: "USA",
  },
};

const { name, age, address } = person;
console.log(name); // "John"
console.log(age); // 30
console.log(address.city); // "New York"
console.log(address.country); // "USA"
```
В этом примере мы декомпозировали объект `person` и извлекли отдельные свойства `name`, `age` и `address`. Мы можем использовать эти переменные отдельно, чтобы получить доступ к значениям свойств объекта.

2. Декомпозиция массива:
```typescript
const colors: string[] = ["red", "green", "blue"];

const [firstColor, secondColor, thirdColor] = colors;
console.log(firstColor); // "red"
console.log(secondColor); // "green"
console.log(thirdColor); // "blue"
```
В этом примере мы декомпозировали массив `colors` и извлекли отдельные элементы. Мы используем `[firstColor, secondColor, thirdColor]` для декомпозиции и присваиваем значениям переменных значения из массива.

3. Декомпозиция типа функции:
```typescript
type MathOperation = (a: number, b: number) => number;

const add: MathOperation = (a, b) => a + b;
const subtract: MathOperation = (a, b) => a - b;

console.log(add(5, 3)); // 8
console.log(subtract(7, 2)); // 5
```
В этом примере мы определили тип `MathOperation` для функции, которая принимает два числовых аргумента и возвращает число. Затем мы декомпозировали тип функции и использовали его для определения функций `add` и `subtract`.

Декомпозиция типов позволяет получать доступ к отдельным частям сложных типов данных в TypeScript. Это полезная возможность, которая помогает упростить код, избегать дублирования и делать код более читаемым.