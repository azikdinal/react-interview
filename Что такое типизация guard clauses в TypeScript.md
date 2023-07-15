Типизация "guard clauses" (охранные выражения) в TypeScript относится к использованию условных проверок для уточнения типов данных внутри функции или метода. Охранные выражения позволяют программисту проверять типы входящих данных и проводить специфические действия, основанные на результатах этих проверок.

Охранные выражения могут применяться в следующих сценариях:

1. Проверка типа с помощью `typeof`:
```typescript
function printValue(value: string | number) {
  if (typeof value === 'string') {
    console.log('The value is a string:', value.toUpperCase());
  } else if (typeof value === 'number') {
    console.log('The value is a number:', value.toFixed(2));
  }
}

printValue('hello'); // The value is a string: HELLO
printValue(42); // The value is a number: 42.00
```

В этом примере охранные выражения используют `typeof` для проверки типа значения `value`. Если `value` является строкой, мы вызываем метод `toUpperCase()`, иначе, если `value` является числом, мы вызываем метод `toFixed(2)`.

2. Проверка наличия свойств:
```typescript
interface Person {
  name: string;
  age?: number;
}

function greet(person: Person) {
  if ('name' in person) {
    console.log('Hello,', person.name);
  }

  if ('age' in person) {
    console.log('Age:', person.age);
  }
}

greet({ name: 'John' }); // Hello, John
greet({ name: 'Jane', age: 30 }); // Hello, Jane // Age: 30
```

В этом примере охранные выражения используют оператор `in` для проверки наличия свойства в объекте `person`. Если свойство `name` присутствует, мы выводим приветствие с именем. Если свойство `age` также присутствует, мы также выводим значение возраста.

3. Проверка на пользовательские типы или свойства:
```typescript
interface Circle {
  kind: 'circle';
  radius: number;
}

interface Square {
  kind: 'square';
  sideLength: number;
}

type Shape = Circle | Square;

function getArea(shape: Shape) {
  if (shape.kind === 'circle') {
    const area = Math.PI * shape.radius ** 2;
    console.log('Circle area:', area);
  } else if (shape.kind === 'square') {
    const area = shape.sideLength ** 2;
    console.log('Square area:', area);
  }
}

getArea({ kind: 'circle', radius: 5 }); // Circle area: 78.53981633974483
getArea({ kind: 'square', sideLength: 4 }); // Square area: 16
```

В этом примере охранные выражения используют свойство `kind` в объектах `Circle` и `Square`, чтобы определить, какой тип фигуры передан в функцию `getArea`. В зависимости от значения свойства `kind`, мы вычисляем площадь круга или квадрата.

Типизация "guard clauses" позволяет вам более точно уточнять типы данных и выполнять соответствующие действия на основе этих проверок. Они позволяют статическому анализатору TypeScript выполнять проверку типов и предоставлять интеллектуальные подсказки и автодополнение в соответствии с проведенными проверками.