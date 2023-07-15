Хук `useContext` в React позволяет вам получить доступ к значению контекста и подписаться на его изменения в функциональном компоненте. Вы можете использовать `useContext` для управления состоянием внутри компонента без необходимости создания отдельного хранилища состояния, такого как Redux или MobX.

Вот пример использования `useContext` для управления состоянием:

1. Создайте контекст с помощью функции `createContext`:

   ```javascript
   import React, { createContext, useState } from 'react';

   const MyContext = createContext();
   ```

2. Оберните свой компонент или иерархию компонентов внутри компонента-провайдера, который предоставляет значение контекста:

   ```javascript
   const App = () => {
     const [state, setState] = useState('initial state');

     return (
       <MyContext.Provider value={{ state, setState }}>
         <ChildComponent />
       </MyContext.Provider>
     );
   };
   ```

   В этом примере компонент `App` является провайдером контекста. Он предоставляет значение контекста (в данном случае состояние `state` и функцию `setState`) дочерним компонентам внутри `<MyContext.Provider>`.

3. Внутри дочерних компонентов вы можете использовать `useContext` для получения значения контекста:

   ```javascript
   import React, { useContext } from 'react';

   const ChildComponent = () => {
     const { state, setState } = useContext(MyContext);

     const handleClick = () => {
       setState('new state');
     };

     return (
       <div>
         <p>Current state: {state}</p>
         <button onClick={handleClick}>Update state</button>
       </div>
     );
   };
   ```

   В этом примере компонент `ChildComponent` использует `useContext` для получения значения контекста. Он может получить текущее состояние `state` и функцию `setState`, которую можно использовать для обновления состояния.

При вызове функции `setState` в компоненте `ChildComponent`, состояние будет обновлено в компоненте `App`, а все компоненты, использующие контекст `MyContext`, будут перерисованы с новым значением.

Использование `useContext` позволяет передавать состояние и функции управления состоянием от родительского компонента к дочерним компонентам без необходимости прокидывания через пропсы. Это удобно, когда у вас есть глубокая иерархия компонентов, и вам нужно передать состояние через несколько уровней компонентов.