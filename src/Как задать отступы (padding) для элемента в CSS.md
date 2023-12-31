В CSS отступы элемента могут быть заданы с использованием свойств `padding-top`, `padding-right`, `padding-bottom` и `padding-left`. Вот несколько способов задания отступов:

1. Одновременное задание всех отступов:
   - Можно задать все отступы одновременно с использованием свойства `padding` и указать значения отступов в порядке верхнего, правого, нижнего и левого (по часовой стрелке).
   - Пример: `padding: 10px 20px 15px 5px;` - задает верхний отступ 10 пикселей, правый отступ 20 пикселей, нижний отступ 15 пикселей и левый отступ 5 пикселей.

2. Отдельное задание каждого отступа:
   - Можно задать каждый отступ отдельно, используя соответствующие свойства `padding-top`, `padding-right`, `padding-bottom` и `padding-left`.
   - Пример: `padding-top: 10px;` - задает верхний отступ 10 пикселей, `padding-right: 20px;` - задает правый отступ 20 пикселей и так далее.

3. Установка одинаковых отступов по всем сторонам:
   - Можно установить одинаковые значения для всех отступов, используя свойство `padding`.
   - Пример: `padding: 10px;` - устанавливает одинаковый отступ в 10 пикселей для всех сторон элемента.

4. Использование относительных значений:
   - Можно использовать относительные значения отступов, такие как проценты или относительные единицы измерения (`em`, `rem`), чтобы отступы масштабировались относительно размеров окружающих элементов.
   - Пример: `padding: 5% 10%;` - устанавливает верхний и нижний отступ в 5% высоты элемента и правый и левый отступ в 10% ширины элемента.

Примеры:
```css
div {
  padding: 10px 20px; /* Одновременное задание верхнего/нижнего и правого/левого отступов */
}

p {
  padding-top: 15px; /* Отдельное задание верхнего отступа */
  padding-bottom: 15px; /* Отдельное задание нижнего отступа */
  padding-left: 10px; /* Отдельное задание левого отступа */
  padding-right: 10px; /* Отдельное задание правого отступа */
}

span {
  padding: 0.5em 1rem; /* Использование относительных значений */
}
```

Задание отступов позволяет контролировать пространство вокруг элементов и создавать желаемый макет и визуальное разделение на веб-странице.