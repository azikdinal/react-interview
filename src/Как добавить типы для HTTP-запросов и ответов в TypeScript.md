Для добавления типов для HTTP-запросов и ответов в TypeScript можно использовать интерфейсы или типы данных. Это позволяет сильно типизировать код, связанный с сетевыми запросами, и обеспечивает статическую проверку типов во время компиляции.

Вот примеры использования типов для HTTP-запросов и ответов:

1. Использование интерфейсов:
```typescript
interface ApiResponse<T> {
  success: boolean;
  data: T;
  error?: string;
}

interface User {
  id: number;
  name: string;
  email: string;
}

async function fetchUserData(): Promise<ApiResponse<User>> {
  const response = await fetch('https://api.example.com/user');
  const data = await response.json();
  return data as ApiResponse<User>;
}
```
В этом примере мы определяем интерфейс `ApiResponse<T>`, который представляет структуру ответа от сервера. Он содержит свойства `success` для обозначения успешности запроса, `data` для данных и, опционально, `error` для сообщения об ошибке. Затем мы определяем интерфейс `User`, представляющий данные пользователя.

Функция `fetchUserData` выполняет запрос к API и ожидает ответ в виде `ApiResponse<User>`. Мы использовали типизацию промиса `Promise<ApiResponse<User>>`, чтобы указать тип возвращаемого значения.

2. Использование типов данных:
```typescript
type ApiResponse<T> = {
  success: boolean;
  data: T;
  error?: string;
};

type User = {
  id: number;
  name: string;
  email: string;
};

async function fetchUserData(): Promise<ApiResponse<User>> {
  const response = await fetch('https://api.example.com/user');
  const data = await response.json();
  return data as ApiResponse<User>;
}
```
В этом примере мы использовали типы данных (`type`) вместо интерфейсов. В остальном, код идентичен предыдущему примеру.

Какие типы использовать (интерфейсы или типы данных) зависит от ваших предпочтений и требований проекта. Оба подхода позволяют определить типы для HTTP-запросов и ответов в TypeScript. Выберите подход, который лучше соответствует вашему коду и стилю разработки.