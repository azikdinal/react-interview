В Next.js вы можете обрабатывать маршруты на стороне сервера (server-side routing) с помощью функции `getServerSideProps`. Эта функция позволяет вам выполнить серверный код для предварительной загрузки данных или выполнения других операций перед рендерингом страницы на стороне сервера. Вот как это работает:

1. Создайте компонент страницы и определите функцию `getServerSideProps` в нем:

```jsx
function MyPage({ data }) {
  // Используйте полученные данные в компоненте страницы
  return (
    <div>
      <h1>{data.title}</h1>
      <p>{data.content}</p>
    </div>
  );
}

export async function getServerSideProps(context) {
  // Выполните серверный код для получения данных
  const res = await fetch('https://api.example.com/data');
  const data = await res.json();

  // Возвращаемые данные будут переданы в компонент страницы в качестве пропсов
  return {
    props: {
      data,
    },
  };
}

export default MyPage;
```

2. В функции `getServerSideProps` вы можете выполнять запросы к API, получать данные из базы данных или выполнять любую другую операцию на сервере для подготовки данных, которые будут переданы компоненту страницы.

3. Возвращаемый объект из функции `getServerSideProps` должен содержать свойство `props`, которое содержит данные, которые будут переданы компоненту страницы в качестве пропсов.

При обращении к странице, Next.js будет вызывать функцию `getServerSideProps` на стороне сервера и передавать контекст запроса. Функция `getServerSideProps` должна быть экспортирована из компонента страницы. Результат выполнения этой функции будет передан компоненту страницы в качестве пропсов и затем отрендерен на стороне сервера перед отправкой клиенту.

Таким образом, вы можете использовать функцию `getServerSideProps` для обработки маршрутов на стороне сервера и выполнения необходимых операций до рендеринга страницы. Это особенно полезно, когда вам требуется динамически загружать данные для каждого запроса или осуществлять аутентификацию и авторизацию на стороне сервера.