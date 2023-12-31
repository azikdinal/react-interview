Сборка (build process) проекта в Next.js происходит во время выполнения команды `next build`. В процессе сборки происходит ряд шагов, включая:

1. Компиляция исходного кода:
   - Next.js компилирует исходный код вашего проекта, включая файлы JavaScript, TypeScript, React-компоненты, страницы и другие ресурсы.
   - Во время компиляции Next.js выполняет проверку типов (для TypeScript проектов) и проверку ошибок.

2. Создание оптимизированных ресурсов:
   - Next.js оптимизирует и упаковывает ваши ресурсы, включая JavaScript, CSS, изображения и другие файлы.
   - JavaScript и CSS файлы минифицируются, удаляются неиспользуемые стили и применяются различные оптимизации для достижения наилучшей производительности.

3. Генерация статических HTML-страниц:
   - Если вы используете статический пререндеринг (Static Generation) в Next.js с помощью функции `getStaticProps` или `getStaticPaths`, процесс сборки включает генерацию статических HTML-страниц на основе этих функций.
   - Каждая страница пререндерится в статический HTML-файл, который затем будет предоставлен при запросе клиентом.

4. Создание серверного бандла:
   - Next.js создает серверный бандл, который используется для обработки запросов на сервере.
   - Этот серверный бандл содержит весь необходимый код и логику для обработки маршрутов, выполнения функций `getServerSideProps`, обработки API запросов и других серверных операций.

5. Кэширование результатов сборки:
   - В процессе сборки Next.js кэширует результаты, чтобы ускорить последующие сборки.
   - При повторном запуске команды `next build` Next.js проверяет изменения файлов и перекомпилирует только необходимые ресурсы.

После завершения сборки проекта, вы можете запустить ваше приложение Next.js с помощью команды `next start` для запуска сервера и предоставления вашего приложения клиентам.

Обратите внимание, что эти шаги могут немного отличаться в зависимости от конфигурации вашего проекта Next.js и используемых функций, таких как серверный рендеринг (Server-side Rendering) или инкрементальная статическая регенерация (Incremental Static Regeneration).