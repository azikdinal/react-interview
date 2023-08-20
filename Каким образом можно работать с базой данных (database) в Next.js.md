В Next.js вы можете работать с базой данных, используя различные подходы и технологии. Вот некоторые из них:

1. Использование серверных API:
   Один из распространенных способов работы с базой данных в Next.js - это создание серверных API, которые обращаются к базе данных и предоставляют данные для вашего клиентского приложения. Вы можете создать эндпоинты API с помощью Node.js и Express или использовать фреймворки, такие как Next.js API Routes или Fastify, чтобы определить API маршруты внутри вашего Next.js приложения.

   Пример использования Next.js API Routes:

   ```jsx
   // pages/api/users.js
   import { getUsersFromDatabase } from '../../utils/db';

   export default function handler(req, res) {
     const users = getUsersFromDatabase();
     res.status(200).json(users);
   }
   ```

   В этом примере, при обращении к эндпоинту `/api/users`, данные пользователей из базы данных возвращаются в формате JSON.

2. Использование ORM (Object-Relational Mapping):
   ORM - это технология, которая позволяет вам работать с базой данных с помощью объектно-ориентированного подхода, а не непосредственно с SQL. Вы можете использовать ORM библиотеки, такие как Sequelize, TypeORM или Prisma, для упрощения работы с базой данных и выполнения операций CRUD (создание, чтение, обновление, удаление).

   Пример использования Prisma:

   ```jsx
   // pages/index.js
   import { PrismaClient } from '@prisma/client';

   const prisma = new PrismaClient();

   export async function getStaticProps() {
     const users = await prisma.user.findMany();
     return {
       props: {
         users,
       },
     };
   }

   function HomePage({ users }) {
     return (
       <ul>
         {users.map((user) => (
           <li key={user.id}>{user.name}</li>
         ))}
       </ul>
     );
   }

   export default HomePage;
   ```

   В этом примере используется Prisma для выполнения запроса к базе данных и получения списка пользователей, которые затем передаются в компонент `HomePage`.

3. Использование сторонних сервисов:
   Вы можете использовать сторонние сервисы баз данных, такие как Firebase, MongoDB Atlas или AWS DynamoDB, для хранения данных вашего приложения. Эти сервисы предоставляют API и библиотеки для работы с базой данных, которые можно использовать в вашем приложении Next.js.

   Пример использования Firebase Realtime Database:

   ```jsx
   // pages/index.js
   import firebase from 'firebase/app';
   import 'firebase/database';

   const firebaseConfig = {
     // Конфигурация Firebase
   };

   if (!firebase.apps.length) {
     firebase.initializeApp(firebaseConfig);
   }

   export async function getStaticProps() {
     const database = firebase.database();
     const snapshot = await database.ref('users').once('value');
     const users = snapshot.val();
     return {
       props: {
         users,
       },
     };
   }

   function HomePage({ users }) {
     return (
       <ul>
         {Object.values(users).map((user) => (
           <li key={user.id}>{user.name}</li>
         ))}
       </ul>
     );
   }

   export default HomePage;
   ```

   В этом примере используется Firebase Realtime Database для получения списка пользователей из базы данных и отображения их в компоненте `HomePage`.

Выберите подход, который лучше всего соответствует вашим потребностям и требованиям для работы с базой данных в вашем приложении Next.js.