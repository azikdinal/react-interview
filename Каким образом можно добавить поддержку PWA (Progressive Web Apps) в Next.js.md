Для добавления поддержки PWA (Progressive Web Apps) в Next.js вы можете выполнить следующие шаги:

1. Установите пакет `next-pwa`:
   Воспользуйтесь командой `npm install next-pwa` или `yarn add next-pwa`, чтобы установить пакет `next-pwa`. Этот пакет обеспечивает интеграцию PWA-функциональности в ваше приложение Next.js.

2. Создайте файл `next.config.js` в корневой папке проекта:
   В этом файле вы можете настроить конфигурацию для поддержки PWA в вашем приложении Next.js. Пример конфигурации:

   ```javascript
   // next.config.js
   const withPWA = require('next-pwa');

   module.exports = withPWA({
     pwa: {
       dest: 'public',
     },
   });
   ```

   В этом примере конфигурация `pwa.dest` указывает директорию, в которую будут сгенерированы файлы PWA во время сборки приложения.

3. Определите манифест приложения (app manifest):
   Манифест приложения определяет метаданные о вашем PWA, такие как имя, иконки, темы и другие свойства. Создайте файл `public/manifest.json` и определите метаданные вашего приложения. Пример манифеста:

   ```json
   // public/manifest.json
   {
     "name": "My App",
     "short_name": "My App",
     "description": "My Progressive Web App",
     "icons": [
       {
         "src": "/icon.png",
         "sizes": "192x192",
         "type": "image/png"
       }
     ],
     "start_url": "/",
     "display": "standalone",
     "background_color": "#ffffff",
     "theme_color": "#000000"
   }
   ```

   В этом примере манифеста определено имя приложения, описание, иконка, стартовый URL, цвет фона и цвет темы.

4. Добавьте иконки приложения:
   Создайте иконки для вашего PWA разных размеров и разместите их в папке `public`. Обычно это иконки с разными размерами, чтобы адаптироваться под разные устройства и платформы.

5. Регистрация Service Worker:
   Чтобы включить поддержку Service Worker, добавьте следующий код в корневой файл вашего приложения, например, `pages/_app.js`:

   ```jsx
   // pages/_app.js
   import { useEffect } from 'react';
   import { useRouter } from 'next/router';

   function MyApp({ Component, pageProps }) {
     const router = useRouter();

     useEffect(() => {
       if ('serviceWorker' in navigator) {
         window.addEventListener('load', () => {
           navigator.serviceWorker.register('/service-worker.js').then((registration) => {
             console.log('Service Worker registered with scope:', registration.scope);
           });
         });
       }
     }, []);

     return <Component {...pageProps} />;
   }

   export default MyApp;
   ```

   В этом примере кода происходит регистрация Service Worker при загрузке приложения.

6. Построение и развертывание приложения:
   Запустите сборку вашего приложения Next.js с помощью команды `npm run build` или `yarn build`. Затем разверните ваше приложение на сервере или хостинг-платформе.

После выполнения этих шагов ваше приложение Next.js будет иметь поддержку PWA. При посещении сайта современным браузером он будет иметь возможность установки как приложение на устройства пользователя и сохранение его на главном экране. Также будут доступны другие функции PWA, такие как офлайн-работа и кэширование ресурсов для улучшенной производительности.