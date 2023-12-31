В CSS анимация может быть создана с использованием свойства `animation`. Для создания анимации в CSS необходимо выполнить следующие шаги:

1. Определение ключевых кадров (keyframes):
   - Ключевые кадры определяют различные состояния анимации на разных моментах времени. Каждый ключевой кадр определяет стили для определенного момента анимации.
   - Используйте правило `@keyframes` для определения ключевых кадров и задания стилей для каждого кадра.
   - Пример:
     ```css
     @keyframes my-animation {
       0% { opacity: 0; }
       50% { opacity: 0.5; }
       100% { opacity: 1; }
     }
     ```
   - В этом примере `my-animation` - это имя анимации, а `0%`, `50%` и `100%` - это ключевые кадры, определяющие изменения стиля от прозрачности 0% до 100%.

2. Применение анимации к элементу:
   - Чтобы применить анимацию к элементу, используйте свойство `animation` с указанием имени анимации и других опций, таких как продолжительность, задержка, количество повторений и другие.
   - Пример:
     ```css
     .my-element {
       animation: my-animation 2s ease-in-out 0s infinite;
     }
     ```
   - В этом примере `my-element` - это класс элемента, к которому применяется анимация, `my-animation` - это имя анимации, `2s` - это продолжительность анимации в 2 секунды, `ease-in-out` - это функция времени, определяющая плавность анимации, `0s` - это задержка перед началом анимации, `infinite` - это количество повторений (в данном случае анимация будет бесконечно повторяться).

3. Дополнительные параметры анимации:
   - В свойстве `animation` можно использовать и другие параметры, такие как `delay` (задержка перед началом анимации), `direction` (направление анимации), `fill-mode` (режим заполнения), `iteration-count` (количество повторений) и другие, чтобы дополнительно настроить анимацию.
   - Пример:
     ```css
     .my-element {
       animation: my-animation 2s ease-in-out 0s infinite alternate;
     }
     ```
   - В этом примере добавлен параметр `alternate`, который указывает, что анимация будет менять направление после каждого цикла.

Примеры:
```css
@keyframes my-animation {
  0% { opacity: 0; }
  50% { opacity: 0.5; }
  100% { opacity: 1; }
}

.my-element {
  animation: my-animation 2s ease-in-out 0s infinite;
}
```

С помощью CSS-анимаций вы можете создавать разнообразные эффекты, движения и переходы, чтобы оживить веб-страницу и сделать ее более интерактивной.