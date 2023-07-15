В функциональных компонентах React есть несколько подходов к управлению состоянием. Вот некоторые из них:

1. Хук `useState`: Хук `useState` позволяет добавить локальное состояние в функциональный компонент. Он возвращает пару значений - текущее состояние и функцию для его обновления. Вы можете использовать эту функцию для изменения состояния компонента.

   ```javascript
   import React, { useState } from 'react';

   const MyComponent = () => {
     const [count, setCount] = useState(0);

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

2. Хук `useReducer`: Хук `useReducer` предоставляет альтернативный способ управления состоянием, особенно для более сложных состояний или когда вам требуется более строгий контроль над обновлением состояния. Он принимает редюсер (reducer) и начальное состояние, возвращает текущее состояние и диспетчер (dispatch) для выполнения действий.

   ```javascript
   import React, { useReducer } from 'react';

   const initialState = { count: 0 };

   const reducer = (state, action) => {
     switch (action.type) {
       case 'INCREMENT':
         return { count: state.count + 1 };
       case 'DECREMENT':
         return { count: state.count - 1 };
       default:
         return state;
     }
   };

   const MyComponent = () => {
     const [state, dispatch] = useReducer(reducer, initialState);

     const increment = () => {
       dispatch({ type: 'INCREMENT' });
     };

     return (
       <div>
         <p>Count: {state.count}</p>
         <button onClick={increment}>Increment</button>
       </div>
     );
   };
   ```

3. Контекст (Context): Контекст в React позволяет передавать данные через дерево компонентов без необходимости явно передавать их через пропсы. Вы можете использовать контекст для создания глобального состояния или передачи данных от родительского компонента к дочерним компонентам.

   ```javascript
   import React, { createContext, useState } from 'react';

   const MyContext = createContext();

   const MyComponent = () => {
     const [count, setCount] = useState(0);

     return (
       <MyContext.Provider value={{ count, setCount }}>
         <ChildComponent />
       </MyContext.Provider>
     );
   };

   const ChildComponent = () => {
     const { count, setCount } = useContext(MyContext);

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

4. Библиотеки управления состоянием: Кроме встроенных хуков и контекста, в React существуют различные библиотеки управления состоянием, такие как Redux, MobX, Zustand и другие. Эти библиотеки предоставляют более мощные инструменты и паттерны для управления состоянием в приложении.

Каждый подход имеет свои преимущества и подходит для различных сценариев. Выбор подхода зависит от сложности состояния, уровня контроля, необходимости глобального доступа к состоянию и личных предпочтений разработчика.