В React компонентах есть несколько способов использовать стили. Вот некоторые из них:

1. Встроенные стили (Inline Styles): Вы можете определить стили непосредственно в JSX-элементе, используя атрибут `style`. Значение атрибута `style` должно быть объектом, где ключи - это CSS свойства в camelCase, а значения - это значения свойств в строковом формате.

```jsx
function MyComponent() {
  const styles = {
    color: 'red',
    fontSize: '16px',
    backgroundColor: 'lightblue'
  };

  return <div style={styles}>Привет, мир!</div>;
}
```

2. Внешние CSS-файлы: Вы можете создать отдельный CSS-файл и подключить его к компоненту. Внешний файл стилей содержит общие стили, которые применяются ко всем компонентам, использующим этот файл.

```jsx
import './styles.css';

function MyComponent() {
  return <div className="my-component">Привет, мир!</div>;
}
```

В файле `styles.css`:

```css
.my-component {
  color: red;
  font-size: 16px;
  background-color: lightblue;
}
```

3. CSS-модули: CSS-модули позволяют связать стили с конкретным компонентом, чтобы избежать конфликтов имен. Каждому компоненту присваивается уникальный идентификатор, который используется для привязки стилей.

```jsx
import styles from './MyComponent.module.css';

function MyComponent() {
  return <div className={styles.myComponent}>Привет, мир!</div>;
}
```

В файле `MyComponent.module.css`:

```css
.myComponent {
  color: red;
  font-size: 16px;
  background-color: lightblue;
}
```

4. CSS-in-JS библиотеки: Существуют также специальные библиотеки, которые предлагают синтаксис CSS внутри JavaScript, позволяя вам создавать и использовать стили напрямую внутри компонентов.

Некоторые из популярных CSS-in-JS библиотек:
- Styled Components: https://styled-components.com/
- Emotion: https://emotion.sh/
- CSS Modules: https://github.com/css-modules/css-modules

Выбор способа использования стилей в React зависит от ваших предпочтений, требований проекта и его масштаба. Каждый из этих способов имеет свои преимущества и может быть более или менее подходящим в зависимости от контекста.