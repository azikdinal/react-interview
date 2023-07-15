Объявление типа (Type Declaration) в TypeScript - это способ определения пользовательского типа данных для переменных, параметров функций, свойств объектов и других элементов кода. Он позволяет разработчикам указывать ожидаемый тип данных и структуру объектов в коде.

В TypeScript есть несколько способов объявления типов:

1. Аннотации типов переменных:
   ```typescript
   let age: number;
   let name: string;
   ```

2. Аннотации типов параметров функций:
   ```typescript
   function greet(name: string) {
     console.log("Hello, " + name);
   }
   ```

3. Аннотации типов возвращаемого значения функции:
   ```typescript
   function add(a: number, b: number): number {
     return a + b;
   }
   ```

4. Интерфейсы (Interfaces):
   ```typescript
   interface Person {
     name: string;
     age: number;
   }

   let person: Person = { name: "John", age: 25 };
   ```

5. Типы-объединения (Union Types):
   ```typescript
   let id: string | number;
   id = "ABC";
   id = 123;
   ```

6. Пользовательские типы (Custom Types):
   ```typescript
   type Point = {
     x: number;
     y: number;
   };

   let p: Point = { x: 10, y: 20 };
   ```

7. Перечисления (Enums):
   ```typescript
   enum Color {
     Red,
     Green,
     Blue,
   }

   let color: Color = Color.Green;
   ```

Объявление типов позволяет TypeScript проводить статическую проверку типов и обнаруживать потенциальные ошибки на этапе компиляции. Он также улучшает инструменты разработки, предоставляя автодополнение кода, подсказки и более точную документацию для API.

Объявления типов в TypeScript помогают разработчикам создавать более надежные, понятные и поддерживаемые приложения, и предоставляют дополнительные возможности для работы с типами данных в сравнении с обычным JavaScript.