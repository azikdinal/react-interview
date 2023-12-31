Медиа-запросы в CSS - это механизм, который позволяет применять различные стили и правила к элементам на основе характеристик устройства, на котором отображается веб-страница. Они позволяют адаптировать внешний вид и макет веб-страницы для разных типов устройств, разрешений экранов и медиа-функций. Медиа-запросы используются для реализации отзывчивого (responsive) дизайна, чтобы страница выглядела и работала оптимально на различных устройствах.

Медиа-запросы определяются с использованием ключевого слова `@media` и содержат условия, которые определяют, когда стили должны применяться. Например, можно определить медиа-запрос для устройств с максимальной шириной экрана не более 600 пикселей следующим образом:

```css
@media (max-width: 600px) {
  /* Стили и правила, применяемые для устройств с шириной экрана до 600px */
}
```

Некоторые распространенные условия медиа-запросов включают:

- Ширина экрана (`width`): `max-width`, `min-width`.
- Высота экрана (`height`): `max-height`, `min-height`.
- Ориентация устройства (`orientation`): `portrait` (вертикальная), `landscape` (горизонтальная).
- Плотность пикселей (`resolution`): `min-resolution`, `max-resolution`.
- Тип устройства (`device-type`): `screen`, `print`, `speech` и другие.
- Функции устройства (`device-features`): `hover`, `pointer`, `grid`, `color` и другие.

Медиа-запросы могут быть вложенными, и вы можете применять стили и правила, определенные внутри медиа-запросов, только когда условия выполнены. Это позволяет создавать адаптивные дизайны, в которых различные стили применяются в зависимости от характеристик устройства, таких как размер экрана, ориентация, плотность пикселей и др.

Пример использования медиа-запросов:

```css
/* Общие стили для всех устройств */

@media (max-width: 600px) {
  /* Стили для устройств с шириной экрана до 600px */
}

@media (min-width: 601px) and (max-width: 1024px) {
  /* Стили для устройств с шириной экрана от 601px до 1024px */
}

@media screen and (orientation: landscape) {
  /* Стили для устройств в горизонтальной ориентации */
}
```

Использование медиа-запросов позволяет создавать адаптивные веб-страницы, которые могут автоматически приспосабливаться к различным типам устройств и обеспечивать лучшее пользовательское взаимодействие и оптимизированный пользовательский опыт.