В JavaScript существует несколько способов создания объектов. Вот несколько примеров:

1. Литеральная нотация объекта: Используется фигурные скобки `{}` для создания объекта, а свойства и их значения указываются внутри них.
   ```javascript
   const obj = { 
     name: "John",
     age: 30,
     sayHello: function() {
       console.log("Hello!");
     }
   };
   ```

2. Конструктор объекта: Можно использовать функцию-конструктор и оператор `new` для создания нового экземпляра объекта.
   ```javascript
   function Person(name, age) {
     this.name = name;
     this.age = age;
     this.sayHello = function() {
       console.log("Hello!");
     };
   }

   const obj = new Person("John", 30);
   ```

3. Object.create(): Метод `Object.create()` позволяет создать новый объект с указанным прототипом.
   ```javascript
   const personProto = {
     sayHello: function() {
       console.log("Hello!");
     }
   };

   const obj = Object.create(personProto);
   obj.name = "John";
   obj.age = 30;
   ```

4. Классы (синтаксис ECMAScript 2015): Можно использовать синтаксис классов для определения объекта.
   ```javascript
   class Person {
     constructor(name, age) {
       this.name = name;
       this.age = age;
     }

     sayHello() {
       console.log("Hello!");
     }
   }

   const obj = new Person("John", 30);
   ```

В каждом из этих примеров создается объект `obj` с различными свойствами и методами. Объекты в JavaScript могут содержать как данные (свойства), так и функциональность (методы), и могут быть созданы с использованием различных подходов в зависимости от конкретных потребностей и предпочтений разработчика.