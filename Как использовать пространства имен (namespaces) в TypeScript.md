Пространства имен (namespaces) в TypeScript представляют собой механизм организации кода, позволяющий группировать логически связанный код в отдельные области с уникальными именами. Пространства имен помогают избегать конфликтов имен между различными частями кода и создают логическую иерархию.

Для использования пространств имен в TypeScript, используйте ключевое слово `namespace` для создания пространства имен и объявления его содержимого.

```typescript
// MyNamespace.ts
namespace MyNamespace {
  export const myVariable = 42;

  export function myFunction() {
    console.log('Hello from MyNamespace!');
  }
}
```

В приведенном выше примере мы создали пространство имен `MyNamespace` в файле `MyNamespace.ts`. Пространство имен содержит переменную `myVariable` и функцию `myFunction`, которые экспортируются с помощью ключевого слова `export`. Теперь мы можем использовать значения из этого пространства имен в других частях кода.

```typescript
// main.ts
import { MyNamespace } from './MyNamespace';

console.log(MyNamespace.myVariable); // Output: 42

MyNamespace.myFunction(); // Output: "Hello from MyNamespace!"
```

В файле `main.ts` мы импортировали пространство имен `MyNamespace` с помощью ключевого слова `import`. Теперь мы можем использовать экспортированные значения, такие как `myVariable` и `myFunction`, с префиксом `MyNamespace`.

Кроме того, пространства имен могут быть вложенными, что позволяет создавать иерархию пространств имен.

```typescript
// MyNamespace.ts
namespace MyNamespace {
  export namespace InnerNamespace {
    export const myVariable = 42;
  }
}
```

```typescript
// main.ts
import { MyNamespace } from './MyNamespace';

console.log(MyNamespace.InnerNamespace.myVariable); // Output: 42
```

В этом примере мы создали вложенное пространство имен `InnerNamespace` внутри пространства имен `MyNamespace`. Затем мы использовали `MyNamespace.InnerNamespace.myVariable` для доступа к переменной `myVariable`.

Пространства имен позволяют организовывать код в логические группы и избегать конфликтов имен. Однако в современном TypeScript наиболее популярным подходом для организации кода является использование модулей, поскольку они обладают более мощными возможностями импорта и экспорта, чем пространства имен.