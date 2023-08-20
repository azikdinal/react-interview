Для создания выпадающего меню с помощью CSS можно использовать комбинацию свойств `display`, `position` и `hover`. Вот простой пример:

HTML:
```html
<ul class="menu">
  <li>
    <a href="#">Главная</a>
  </li>
  <li>
    <a href="#">О нас</a>
    <ul class="submenu">
      <li><a href="#">История</a></li>
      <li><a href="#">Команда</a></li>
      <li><a href="#">Миссия</a></li>
    </ul>
  </li>
  <li>
    <a href="#">Услуги</a>
  </li>
</ul>
```

CSS:
```css
.menu {
  list-style: none;
  padding: 0;
}

.menu > li {
  display: inline-block;
  position: relative;
}

.menu > li > a {
  display: block;
  padding: 10px;
  text-decoration: none;
  color: #000;
}

.submenu {
  display: none;
  position: absolute;
  top: 100%;
  left: 0;
  padding: 0;
}

.menu > li:hover .submenu {
  display: block;
}

.submenu li {
  display: block;
}

.submenu li a {
  padding: 10px;
  background-color: #f2f2f2;
  color: #000;
  text-decoration: none;
}
```

В этом примере у нас есть список `ul` с классом `.menu`. Каждый пункт меню - `li` содержит ссылку `<a>`. Пункты меню, которые имеют подменю, содержат вложенный список `ul` с классом `.submenu`.

CSS-стили задают основной вид меню и подменю. С помощью свойства `position: relative;` у родительских пунктов меню и `position: absolute;` у подменю мы устанавливаем контекст позиционирования. Затем, при наведении курсора на пункт меню, мы используем селектор `.menu > li:hover .submenu` для отображения подменю, изменяя свойство `display` на `block`.

Вы можете дальше настраивать стили и внешний вид меню, добавлять анимации, различные эффекты и т.д. для достижения желаемого дизайна выпадающего меню.