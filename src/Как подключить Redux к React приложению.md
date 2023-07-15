Для подключения Redux к React приложению вам понадобятся следующие шаги:

1. Установка зависимостей: Убедитесь, что у вас установлены пакеты `redux` и `react-redux`. Вы можете установить их с помощью npm или yarn команды:

   ```bash
   npm install redux react-redux
   ```

   или

   ```bash
   yarn add redux react-redux
   ```

2. Создание хранилища: Создайте хранилище, используя функцию `createStore` из пакета `redux` и передайте в нее корневой редюсер вашего приложения. Редюсеры могут быть объединены с помощью функции `combineReducers`, если у вас есть несколько редюсеров.

   ```javascript
   import { createStore } from 'redux';
   import rootReducer from './reducers';

   const store = createStore(rootReducer);
   ```

3. Подключение хранилища к приложению: Оберните ваше приложение в компонент `Provider` из пакета `react-redux` и передайте хранилище через свойство `store`. Это позволит всем компонентам в вашем приложении получить доступ к хранилищу Redux.

   ```javascript
   import React from 'react';
   import ReactDOM from 'react-dom';
   import { Provider } from 'react-redux';
   import App from './App';
   import store from './store';

   ReactDOM.render(
     <Provider store={store}>
       <App />
     </Provider>,
     document.getElementById('root')
   );
   ```

4. Подключение компонентов: В компонентах вашего приложения вы можете использовать функции `connect` из пакета `react-redux` для подключения компонентов к хранилищу Redux и получения доступа к состоянию и действиям.

   ```javascript
   import React from 'react';
   import { connect } from 'react-redux';

   const MyComponent = ({ counter, incrementCounter }) => {
     return (
       <div>
         <p>Counter: {counter}</p>
         <button onClick={incrementCounter}>Increment</button>
       </div>
     );
   };

   const mapStateToProps = (state) => {
     return {
       counter: state.counter
     };
   };

   const mapDispatchToProps = (dispatch) => {
     return {
       incrementCounter: () => dispatch({ type: 'INCREMENT_COUNTER' })
     };
   };

   export default connect(mapStateToProps, mapDispatchToProps)(MyComponent);
   ```

   В этом примере `mapStateToProps` отображает состояние из хранилища на свойства компонента, а `mapDispatchToProps` отображает действия на свойства компонента. Функция `connect` связывает компонент с хранилищем Redux и обновляет компонент при изменении состояния или выполнении действий.

Теперь ваше React приложение подключено к Redux и готово для использования глобального состояния и действий в компонентах. Вы можете создавать действия, определять редюсеры и использовать хранилище Redux для управления состоянием вашего приложения.