# React Router

**React Router** est la solution la plus populaire pour ajouter du **routing** (navigation entre plusieurs pages) dans une application React.

---

## Installation de React Router

Pour ajouter **React Router** à votre projet, utilisez la commande suivante dans le terminal :

```bash
npm i -D react-router-dom
```

Si vous migrez depuis la version 5, utilisez :

```bash
npm i -D react-router-dom@latest
```

---

## Structure du projet

Pour une application avec plusieurs pages, créez un dossier **`pages`** dans le dossier **`src`**. Voici la structure suggérée :  
```
src/
 └── pages/
     ├── Layout.js
     ├── Home.js
     ├── Blogs.js
     ├── Contact.js
     └── NoPage.js
```

Chaque fichier contiendra un composant React simple correspondant à une page de l'application.

---

## Exemple d'utilisation basique

Nous allons ajouter **React Router** dans le fichier **`index.js`**.

### index.js

```javascript
import ReactDOM from "react-dom/client";
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Layout from "./pages/Layout";
import Home from "./pages/Home";
import Blogs from "./pages/Blogs";
import Contact from "./pages/Contact";
import NoPage from "./pages/NoPage";

export default function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Layout />}>
          <Route index element={<Home />} />
          <Route path="blogs" element={<Blogs />} />
          <Route path="contact" element={<Contact />} />
          <Route path="*" element={<NoPage />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

---

### Explication de l'exemple

1. **`<BrowserRouter>`** : Permet de gérer la navigation de l’application.
2. **`<Routes>`** : Contient plusieurs routes.
3. **`<Route>`** : Définit une route spécifique. Les **Routes imbriquées** héritent du chemin de leur parent :
   - `/blogs` devient accessible via `/ + blogs`.
   - **`index`** : Spécifie la route par défaut d’un parent (ici `/`).
   - **`path="*"`** : Capture toutes les routes non définies (par exemple une **page 404**).

---

## Création des pages / composants

Chaque page est un composant React simple.

### Layout.js  
Le **composant de layout** partage un menu de navigation entre les pages. Il utilise :
- **`<Outlet>`** : Affiche la page enfant correspondante.
- **`<Link>`** : Crée des liens internes en gardant l’historique de navigation. On utilise `<Link>` au lieu de `<a>`.

```javascript
import { Outlet, Link } from "react-router-dom";

const Layout = () => {
  return (
    <>
      <nav>
        <ul>
          <li>
            <Link to="/">Home</Link>
          </li>
          <li>
            <Link to="/blogs">Blogs</Link>
          </li>
          <li>
            <Link to="/contact">Contact</Link>
          </li>
        </ul>
      </nav>

      <Outlet />
    </>
  );
};

export default Layout;
```

---

### Home.js

```javascript
const Home = () => {
  return <h1>Home</h1>;
};

export default Home;
```

---

### Blogs.js

```javascript
const Blogs = () => {
  return <h1>Blog Articles</h1>;
};

export default Blogs;
```

---

### Contact.js

```javascript
const Contact = () => {
  return <h1>Contact Me</h1>;
};

export default Contact;
```

---

### NoPage.js

```javascript
const NoPage = () => {
  return <h1>404</h1>;
};

export default NoPage;
```
