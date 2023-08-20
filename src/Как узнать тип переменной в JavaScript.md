В JavaScript для определения типа переменной можно использовать оператор `typeof`. Он возвращает строку, указывающую тип значения переменной. Вот несколько примеров:

1. Число:
   ```javascript
   const num = 42;
   console.log(typeof num); // "number"
   ```

2. Строка:
   ```javascript
   const str = "Hello, world!";
   console.log(typeof str); // "string"
   ```

3. Булево значение:
   ```javascript
   const bool = true;
   console.log(typeof bool); // "boolean"
   ```

4. Объект:
   ```javascript
   const obj = { name: "John" };
   console.log(typeof obj); // "object"
   ```

5. Массив:
   ```javascript
   const arr = [1, 2, 3];
   console.log(typeof arr); // "object"
   ```

6. Функция:
   ```javascript
   function func() {
     console.log("Hello!");
   }
   console.log(typeof func); // "function"
   ```

7. `null`:
   ```javascript
   const nullValue = null;
   console.log(typeof nullValue); // "object"
   ```

8. `undefined`:
   ```javascript
   let undefinedValue;
   console.log(typeof undefinedValue); // "undefined"
   ```

Оператор `typeof` возвращает строку, указывающую на основной тип значения переменной. Однако, стоит отметить, что оператор `typeof` имеет некоторые особенности, например, он возвращает `"object"` как результат для массивов и `null`. Также он не может различать между различными подтипами объектов. При работе с объектами, массивами или пользовательскими классами рекомендуется использовать другие методы, такие как `Array.isArray()`, оператор `instanceof` или дополнительные проверки, чтобы получить более точную информацию о типе переменной.