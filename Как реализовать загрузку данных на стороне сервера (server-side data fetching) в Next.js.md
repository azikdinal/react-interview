В Next.js вы можете реализовать загрузку данных на стороне сервера (server-side data fetching) с помощью двух подходов: `getServerSideProps` и `getInitialProps`.

1. **getServerSideProps**:
   `getServerSideProps` используется для загрузки данных на стороне сервера при каждом запросе страницы. Вы определяете эту функцию внутри компонента страницы и она будет вызываться на сервере при каждом запросе страницы.

   Пример использования `getServerSideProps`:

   ```jsx
   function HomePage({ data }) {
     return (
       <div>
         <h1>Welcome to the HomePage</h1>
         <p>{data}</p>
       </div>
     );
   }

   export async function getServerSideProps() {
     const res = await fetch('https://api.example.com/data');
     const data = await res.json();

     return {
       props: {
         data,
       },
     };
   }

   export default HomePage;
   ```

   В этом примере `getServerSideProps` выполняет асинхронный запрос к API, получает данные и передает их в компонент `HomePage` через `props`.

2. **getInitialProps** (устаревший подход):
   `getInitialProps` является устаревшим подходом и рекомендуется использовать `getServerSideProps` вместо него. Однако, если вы работаете с версией Next.js ниже 9.3 или в случае необходимости использования этого подхода, вы можете определить `getInitialProps` внутри компонента страницы.

   Пример использования `getInitialProps`:

   ```jsx
   function HomePage({ data }) {
     return (
       <div>
         <h1>Welcome to the HomePage</h1>
         <p>{data}</p>
       </div>
     );
   }

   HomePage.getInitialProps = async () => {
     const res = await fetch('https://api.example.com/data');
     const data = await res.json();

     return {
       data,
     };
   };

   export default HomePage;
   ```

   Обратите внимание, что `getInitialProps` должен быть асинхронной функцией и возвращать объект с данными, которые будут переданы в компонент страницы через `props`.

В обоих подходах (`getServerSideProps` и `getInitialProps`) вы можете выполнить асинхронные запросы к API, базам данных или любым другим источникам данных на стороне сервера и передать полученные данные в компонент страницы для их отображения. Это особенно полезно, когда вам требуется получить данные, которые зависят от параметров запроса или должны быть загружены динамически на каждом запросе страницы.