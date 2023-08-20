В Next.js вы можете управлять метаданными, такими как заголовки страницы, с помощью нескольких подходов. Вот некоторые из них:

1. Использование компонента `<Head>`:
   В компоненте страницы вы можете использовать компонент `<Head>` из пакета `next/head`, чтобы управлять метаданными, такими как заголовок страницы, мета-теги, стили и другие элементы `<head>` в HTML.

   Пример использования `<Head>`:

   ```jsx
   import Head from 'next/head';

   function MyPage() {
     return (
       <div>
         <Head>
           <title>Заголовок страницы</title>
           <meta name="description" content="Описание страницы" />
           {/* Другие мета-теги и элементы */}
         </Head>
         <h1>Содержимое страницы</h1>
       </div>
     );
   }

   export default MyPage;
   ```

   Эти метаданные будут вставлены в `<head>` на сервере и переданы в браузер для отображения.

2. Использование функции `getStaticProps` или `getServerSideProps`:
   Вы можете использовать методы `getStaticProps` или `getServerSideProps` в вашем компоненте страницы для получения данных, включая метаданные, с сервера перед рендерингом страницы. Вы можете передать эти данные в компонент страницы через свойство `props`.

   Пример использования `getStaticProps`:

   ```javascript
   export async function getStaticProps() {
     const pageData = await fetchPageData();
     return {
       props: {
         pageData
       }
     };
   }

   function MyPage({ pageData }) {
     return (
       <div>
         <Head>
           <title>{pageData.title}</title>
           <meta name="description" content={pageData.description} />
           {/* Другие мета-теги и элементы */}
         </Head>
         <h1>Содержимое страницы</h1>
       </div>
     );
   }

   export default MyPage;
   ```

   В этом примере данные, включая заголовок страницы и описание, получаются с сервера при использовании `getStaticProps` и передаются в компонент страницы через свойство `props`.

3. Использование специальных компонентов шаблонов:
   Если вы используете компоненты шаблонов в вашем приложении, вы можете передавать метаданные через свойства компонента шаблона и использовать их для управления заголовками страниц.

   Пример использования компонента шаблона:

   ```jsx
   import Head from 'next/head';

   function Layout({ title, description, children }) {
     return (
       <div>
         <Head>
           <title>{title}</title>
           <meta name="description" content={description} />
           {/* Другие мета-теги и элементы */}
         </Head>
         {children}
       </div>
     );
   }

   function MyPage() {
     return (
       <Layout title="Заголовок страницы" description="Описание страницы">
         <h1>Содержимое страницы</h1>
       </Layout>
     );
   }

   export default MyPage;
   ```

   В этом примере метаданные передаются в компонент шаблона через свойства `title` и `description`, а затем использованы в компоненте `<Head>`.

Вы можете выбрать подход, который лучше всего соответствует вашим потребностям и использовать его для управления метаданными и заголовками страниц в вашем приложении Next.js.