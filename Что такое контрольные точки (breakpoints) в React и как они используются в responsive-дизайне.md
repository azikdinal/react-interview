Контрольные точки (breakpoints) в React используются в responsive-дизайне для адаптации компонентов и макетов к различным размерам экранов или устройств. Они представляют собой определенные значения ширины экрана, на которых осуществляется изменение стилизации и компоновки элементов.

В React существуют различные подходы к использованию контрольных точек в responsive-дизайне:

1. Медиа-запросы CSS:
   Один из распространенных способов использования контрольных точек в React - это с помощью медиа-запросов CSS. Вы можете определить CSS-стили для разных контрольных точек, используя `@media`-правила внутри CSS-файлов или внутри компонентов с помощью CSS-модулей или других подобных подходов.

   Пример использования медиа-запросов CSS в React компоненте:

   ```jsx
   import React from 'react';
   import styles from './MyComponent.module.css';

   const MyComponent = () => {
     return (
       <div className={styles.container}>
         <h1 className={styles.title}>Hello, World!</h1>
       </div>
     );
   };

   export default MyComponent;
   ```

   ```css
   /* MyComponent.module.css */
   .container {
     display: flex;
     justify-content: center;
   }

   .title {
     font-size: 24px;
   }

   @media (min-width: 768px) {
     .container {
       flex-direction: row;
     }

     .title {
       font-size: 32px;
     }
   }
   ```

   В этом примере компонент `MyComponent` использует CSS-модули для применения разных стилей в зависимости от ширины экрана.

2. Использование библиотек:
   Вы также можете использовать библиотеки, такие как `react-responsive` или `styled-components`, которые предоставляют удобные компоненты и хуки для работы с контрольными точками в React.

   Пример использования `react-responsive`:

   ```jsx
   import React from 'react';
   import { useMediaQuery } from 'react-responsive';

   const MyComponent = () => {
     const isMobile = useMediaQuery({ maxWidth: 768 });

     return (
       <div>
         {isMobile ? <h1>Hello, Mobile!</h1> : <h1>Hello, Desktop!</h1>}
       </div>
     );
   };

   export default MyComponent;
   ```

   В этом примере хук `useMediaQuery` из `react-responsive` используется для определения, соответствует ли ширина экрана заданному условию. В зависимости от результата, компонент рендерит разные элементы.

Контрольные точки в responsive-дизайне позволяют создавать адаптивные компоненты, которые могут адекватно реагировать на различные размеры экранов и устройств. Они позволяют создавать более гибкие и удобные пользовательские интерфейсы, которые отлично работают на различных устройствах.