Условные типы (conditional types) в TypeScript позволяют создавать типы, которые зависят от условий или проверок на основе других типов. Они позволяют создавать более гибкие и переиспользуемые типы, которые адаптируются к различным сценариям.

Синтаксис условных типов выглядит следующим образом:

```typescript
T extends U ? X : Y
```

Здесь `T` и `U` - это типы, а `X` и `Y` - это типы, которые возвращаются, в зависимости от того, выполняется ли условие `T extends U`. Если условие истинно, то возвращается тип `X`, иначе - тип `Y`.

Вот несколько примеров использования условных типов:

1. Проверка типа:
```typescript
type TypeName<T> =
  T extends string ? 'string' :
  T extends number ? 'number' :
  T extends boolean ? 'boolean' :
  'unknown';

type Type1 = TypeName<string>; // 'string'
type Type2 = TypeName<42>; // 'number'
type Type3 = TypeName<true>; // 'boolean'
type Type4 = TypeName<{}>; // 'unknown'
```

В этом примере мы создали условный тип `TypeName`, который проверяет тип `T` и возвращает соответствующую строку-метку. Если тип `T` является строкой, возвращается `'string'`, если число - `'number'`, если булево значение - `'boolean'`, иначе - `'unknown'`.

2. Выделение свойств объекта:
```typescript
type ExtractProperties<T> = {
  [K in keyof T]: T[K] extends Function ? never : T[K];
};

interface MyObject {
  id: number;
  name: string;
  getDate: () => Date;
}

type ExtractedProps = ExtractProperties<MyObject>;
// { id: number, name: string }
```

В этом примере мы создали условный тип `ExtractProperties`, который принимает объектный тип `T` и возвращает новый тип, исключая все свойства, которые являются функциями. Таким образом, тип `ExtractedProps` содержит только свойства, которые не являются функциями.

3. Определение типа аргумента функции:
```typescript
type ArgumentType<T> = T extends (arg: infer U) => any ? U : never;

function greet(name: string) {
  console.log(`Hello, ${name}!`);
}

type GreetArgument = ArgumentType<typeof greet>; // string
```

В этом примере мы создали условный тип `ArgumentType`, который принимает тип `T` и возвращает тип аргумента функции, если `T` является функцией. Мы использовали ключевое слово `infer`, чтобы TypeScript сам определил тип аргумента. В результате, тип `GreetArgument` стал равен `string`, так как аргумент функции `greet` имеет тип `string`.

Условные типы являются мощным инструментом в TypeScript, который позволяет создавать гибкие и адаптивные типы данных. Они могут использоваться для различных задач, включая проверку типов, обработку свойств объектов, вывод типов и многое другое.