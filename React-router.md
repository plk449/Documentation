# Step - 1

i. npm i react-router-dom

# Step - 2

src/Layout.jsx

```javascript
import { Navbar, Footer } from "./components";
import { Outlet } from "react-router-dom";

function Layout() {
  return (
    <div>
      <Navbar />
      <Outlet />
      <Footer />
    </div>
  );
}

export default Layout;
```

# Step - 3

src/main.jsx or src/app.jsx

```javascript
import { createBrowserRouter, RouterProvider } from "react-router-dom";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Layout />,
    children: [
      {
        path: "",
        element: <Home />,
      },
      {
        path: "about",
        element: <About />,
      },
    ],
  },
]);

// Or

const router = createBrowserRouter(
  createRoutesFromElements(
    <Route path="/" element={<Layout />}>
      <Route path="" element={<Home />} />
      <Route path="about" element={<About />} />
      <Route path="contact" element={<Contact />} />
    </Route>
  )
);

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <RouterProvider router={router} />
  </StrictMode>
);
```

# Step - 4

<h4>It always Good to create an error page component</h4>

<li>src/Error-page.jsx

```javascript
import { useRouteError } from "react-router-dom";

export default function ErrorPage() {
  const error = useRouteError();
  console.error(error);

  return (
    <div id="error-page">
      <h1>Oops!</h1>
      <p>Sorry, an unexpected error has occurred.</p>
      <p>
        <i>{error.statusText || error.message}</i>
      </p>
    </div>
  );
}
```

<li>👉 Set the <ErrorPage> as the errorElement on the root route

```javascript
const router = createBrowserRouter([
  {
    path: "/",
    element: <Layoutoot />,
    errorElement: <ErrorPage />,
  },
  {
    path: "contacts/:contactId",
    element: <Contact />,
  },
]);
```
