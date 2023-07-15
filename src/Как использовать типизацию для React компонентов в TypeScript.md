Для типизации React компонентов в TypeScript можно использовать типы и интерфейсы. TypeScript позволяет явно указывать типы для пропсов (props) компонента, а также для состояния (state), контекста (context) и других аспектов компонентов.

Вот несколько способов использования типизации для React компонентов в TypeScript:

1. Использование типа для пропсов компонента:
```typescript
import React from 'react';

interface MyComponentProps {
  name: string;
  age: number;
}

const MyComponent: React.FC<MyComponentProps> = ({ name, age }) => {
  return (
    <div>
      <p>Name: {name}</p>
      <p>Age: {age}</p>
    </div>
  );
};
```
В этом примере мы определяем интерфейс `MyComponentProps`, который указывает типы для пропсов компонента. Затем мы используем `React.FC<MyComponentProps>` для указания, что `MyComponent` является функциональным компонентом с указанными пропсами.

2. Использование обобщений (generics) для пропсов компонента:
```typescript
import React from 'react';

interface MyComponentProps<T> {
  data: T;
}

const MyComponent: React.FC<MyComponentProps<string>> = ({ data }) => {
  return <div>Data: {data}</div>;
};
```
В этом примере мы используем обобщение (generic) `T` для обозначения типа данных, передаваемого в пропс `data`. Мы используем `React.FC<MyComponentProps<string>>` для указания, что `MyComponent` принимает пропс с типом `MyComponentProps<string>`, где `string` - это тип данных для `data`.

3. Использование хуков (hooks) с типизацией:
```typescript
import React, { useState } from 'react';

interface CounterProps {
  initialValue: number;
}

const Counter: React.FC<CounterProps> = ({ initialValue }) => {
  const [count, setCount] = useState(initialValue);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
};
```
В этом примере мы определяем тип `CounterProps` для пропсов компонента `Counter`. Затем мы используем `useState` хук для создания состояния `count` и функции `setCount`, с указанием типа данных для `initialValue`. Далее, мы используем типизированные пропсы и состояние внутри компонента.

Типизация React компонентов в TypeScript позволяет предотвратить ошибки и обеспечить более надежную разработку. Она также предоставляет статическую проверку типов и интеллектуальные подсказки при работе с компонентами. Используйте типы и интерфейсы для явного указания типов пропсов, состояния и других аспектов ваших компонентов.