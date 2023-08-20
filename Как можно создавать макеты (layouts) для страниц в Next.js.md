В Next.js есть несколько способов создания макетов (layouts) для страниц. Вот некоторые из них:

1. Использование компонента высшего порядка (Higher-Order Component - HOC):
   Вы можете создать HOC, который будет оборачивать ваши страницы и предоставлять общую структуру или компоненты макета. HOC может содержать общие элементы, такие как шапка, навигационное меню или подвал, которые будут отображаться на всех страницах.

   Пример создания HOC:

   ```jsx
   // components/Layout.js
   import Header from './Header';
   import Footer from './Footer';

   const Layout = (PageComponent) => {
     return () => (
       <div>
         <Header />
         <PageComponent />
         <Footer />
       </div>
     );
   };

   export default Layout;
   ```

   ```jsx
   // pages/about.js
   import Layout from '../components/Layout';

   const AboutPage = () => {
     return <h1>About Page</h1>;
   };

   export default Layout(AboutPage);
   ```

   В этом примере `Layout` является HOC, который оборачивает компонент `AboutPage` и добавляет общую структуру страницы с шапкой и подвалом.

2. Использование компонента `<Layout>`:
   Вы можете создать компонент `<Layout>`, который будет использоваться на каждой странице в качестве обертки. Это позволяет вам определить общую структуру страницы и использовать ее повторно на разных страницах.

   Пример создания компонента `<Layout>`:

   ```jsx
   // components/Layout.js
   import Header from './Header';
   import Footer from './Footer';

   const Layout = ({ children }) => {
     return (
       <div>
         <Header />
         {children}
         <Footer />
       </div>
     );
   };

   export default Layout;
   ```

   ```jsx
   // pages/about.js
   import Layout from '../components/Layout';

   const AboutPage = () => {
     return (
       <Layout>
         <h1>About Page</h1>
       </Layout>
     );
   };

   export default AboutPage;
   ```

   В этом примере компонент `<Layout>` является оберткой для компонента `AboutPage` и добавляет общую структуру страницы.

3. Использование маршрутизатора:
   Если вы используете маршрутизатор, такой как React Router, вы можете определить макеты для разных маршрутов. В этом случае вы можете указать разные компоненты макета для разных маршрутов, чтобы отобразить различные макеты на разных страницах.

   Пример с использованием React Router:

   ```jsx
   // components/Layout.js
   import Header from './Header';
   import Footer from './Footer';

   const Layout = ({ children }) => {
     return (
       <div>
         <Header />
         {children}
         <Footer />
       </div>
     );
   };

   export default Layout;
   ```

   ```jsx
   // pages/about.js
   import Layout from '../components/Layout';

   const AboutPage = () => {
     return <h1>About Page</h1>;
   };

   export default AboutPage;
   ```

   ```jsx
   // App.js
   import { BrowserRouter as Router, Route } from 'react-router-dom';
   import Layout from './components/Layout';
   import HomePage from './pages/Home';
   import AboutPage from './pages/About';

   function App() {
     return (
       <Router>
         <Layout>
           <Route exact path="/" component={HomePage} />
           <Route exact path="/about" component={AboutPage} />
         </Layout>
       </Router>
     );
   }

   export default App;
   ```

   В этом примере компонент `Layout` оборачивает компоненты страниц, определенные в маршрутах React Router.

Выберите подход, который лучше всего соответствует вашим потребностям и требованиям для создания макетов страниц в вашем приложении Next.js.