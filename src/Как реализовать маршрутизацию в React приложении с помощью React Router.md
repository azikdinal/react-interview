Для реализации маршрутизации в React приложении вы можете использовать библиотеку React Router. Вот базовый пример того, как настроить маршрутизацию с использованием React Router:

1. Установите React Router:
   Выполните команду `npm install react-router-dom` для установки пакета React Router DOM.

2. Создайте основной компонент маршрутизации:
   Создайте новый компонент, который будет являться основным компонентом для маршрутизации. Этот компонент будет содержать `<BrowserRouter>` (или `<HashRouter>`) и определит основные маршруты вашего приложения.

```jsx
import React from 'react';
import { BrowserRouter, Route, Switch } from 'react-router-dom';

import Home from './components/Home';
import About from './components/About';
import Contact from './components/Contact';

const App = () => {
  return (
    <BrowserRouter>
      <Switch>
        <Route exact path="/" component={Home} />
        <Route path="/about" component={About} />
        <Route path="/contact" component={Contact} />
      </Switch>
    </BrowserRouter>
  );
};

export default App;
```

3. Создайте компоненты для каждого маршрута:
   Создайте отдельные компоненты для каждого маршрута, которые будут отображаться при переходе по соответствующему пути.

4. Добавьте навигацию:
   Добавьте навигацию между маршрутами в ваше приложение. Вы можете использовать компоненты `<Link>` или `<NavLink>` из React Router для создания ссылок на различные маршруты.

```jsx
import React from 'react';
import { Link } from 'react-router-dom';

const Navigation = () => {
  return (
    <nav>
      <ul>
        <li>
          <Link to="/">Home</Link>
        </li>
        <li>
          <Link to="/about">About</Link>
        </li>
        <li>
          <Link to="/contact">Contact</Link>
        </li>
      </ul>
    </nav>
  );
};

export default Navigation;
```

5. Используйте маршрутизацию в компонентах:
   В нужных компонентах вы можете использовать компоненты `<Route>` или хуки `useRouteMatch`, `useParams` и другие хуки из React Router для получения информации о текущем маршруте или параметрах URL.

Это лишь базовый пример использования React Router для маршрутизации в React приложении. Вы можете использовать более сложные конфигурации, вложенные маршруты, защищенные маршруты и другие возможности, предоставляемые React Router. Документация React Router (https://reactrouter.com/) предоставляет подробную информацию о всех возможностях и настройках библиотеки.