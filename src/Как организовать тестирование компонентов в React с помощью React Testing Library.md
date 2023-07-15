Для тестирования компонентов в React вы можете использовать библиотеку React Testing Library. Она предоставляет простой и интуитивно понятный API для написания тестов, сфокусированных на поведении компонентов в реальных сценариях использования. Вот основные шаги для организации тестирования компонентов с использованием React Testing Library:

1. Установите React Testing Library в ваш проект:
   ```
   npm install --save-dev @testing-library/react
   ```

2. Создайте файлы тестовых сценариев (тестов) для ваших компонентов. Обычно их располагают в папке `__tests__` рядом с компонентами или в отдельной папке `tests`. Например, `Button.test.js`:
   ```jsx
   import React from 'react';
   import { render, fireEvent } from '@testing-library/react';
   import Button from '../Button';

   test('renders button correctly', () => {
     const { getByText } = render(<Button label="Click me" />);
     const button = getByText('Click me');

     expect(button).toBeInTheDocument();
   });

   test('calls onClick handler when clicked', () => {
     const handleClick = jest.fn();
     const { getByText } = render(<Button label="Click me" onClick={handleClick} />);
     const button = getByText('Click me');

     fireEvent.click(button);

     expect(handleClick).toHaveBeenCalledTimes(1);
   });
   ```

3. В файлах тестов используйте функции `render`, `fireEvent` и другие из React Testing Library для рендеринга компонентов, взаимодействия с ними и проверки ожидаемых результатов. Например, функция `render` используется для рендеринга компонента, а `fireEvent.click` - для эмуляции клика на элементе. Затем, с помощью функций `getByText` или других, вы можете получить ссылки на элементы и выполнить проверки с использованием функций утверждений, таких как `expect`.

4. Запустите тесты с помощью инструмента для запуска тестов, такого как Jest:
   ```
   npm test
   ```

React Testing Library предлагает еще много других полезных функций и методов для тестирования компонентов, таких как получение элементов по атрибутам, проверка наличия или отсутствия элементов, тестирование состояний и многое другое. Она специально разработана для тестирования компонентов в реальных условиях использования, чтобы ваши тесты были более подробными и отражали реальное поведение компонентов.