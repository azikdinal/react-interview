Представительские компоненты (presentational components) в Redux - это компоненты React, которые отвечают за отображение пользовательского интерфейса и презентацию данных, но не содержат логику управления состоянием или взаимодействия с хранилищем Redux.

Основные характеристики представительских компонентов:

1. Фокус на отображении: Представительские компоненты фокусируются на том, как данные отображаются и как пользовательский интерфейс выглядит. Они принимают данные в виде свойств (props) и рендерят их, предоставляя пользовательский интерфейс, который отражает текущее состояние.

2. Без зависимости от состояния: Представительские компоненты не содержат собственного состояния и не имеют прямого доступа к хранилищу Redux. Они получают данные и обратные вызовы (callback) через свойства (props) и используют их для отображения и взаимодействия с пользователем.

3. Повторное использование и гибкость: Представительские компоненты обычно являются переиспользуемыми, что позволяет легко добавлять и изменять компоненты интерфейса без влияния на управление состоянием. Они могут быть гибко настроены с помощью свойств (props) для отображения разных данных или поведения.

Пример представительской компоненты:

```javascript
import React from 'react';

const CounterDisplay = ({ counter }) => {
  return (
    <div>
      <p>Counter: {counter}</p>
    </div>
  );
};

export default CounterDisplay;
```

В этом примере `CounterDisplay` - это представительская компонента, которая принимает свойство `counter` и отображает его внутри элемента `<p>`. Она не имеет собственного состояния и не взаимодействует напрямую с хранилищем Redux. Вместо этого она полагается на свойства, которые передаются из контейнерной компоненты или родительского компонента.

Использование представительских компонентов помогает разделить ответственности и обеспечить более простую и понятную архитектуру приложения. Они сосредотачиваются на отображении данных и поведении пользовательского интерфейса, в то время как контейнерные компоненты управляют состоянием и взаимодействием с Redux.