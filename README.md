# React-router-dom
Its a library that helps us to add routing to our react app that runs in browser. React is a Single Page Application (SPA) framework which means: there is only one HTML page but we still want multiple screens or pages for which React-router-dom will let us do by  dynamically rendering components based on URL withour reloading the page.

npm install react-router-dom

# Routing

### React v6.3
uses component based routing 
JSX inside <Routes>
``` routing
import { BrowserRouter, Routes, Route } from 'react-router-dom';

<BrowserRouter>
  <Routes>
    <Route path = "/" element = { < Home />} />
    <Route path="/about" element={<About />} />
  </Routes>
</BrowserRouter> 
```
### React v6.4+
uses data aware routing with route configuration object
JSON like object in a router

``` routing
import {
createBrowserRouter,RouterProvider,createRoutesFromElements,Route,Outlet,redirect
} from 'react-router-dom';
const router = createBrowserRouter([
  {
    path: "/",
    element: <App />,
    errorElement: <ErrorPage />,
    children: [
      {
        path: "",
        element: <Home />,
        loader: homeLoader,
      },
      {
        path: "about",
        element: <About />
      }
    ]
  }
]);
ReactDOM.createRoot(document.getElementById('root')).render(
  <RouterProvider router={router} />
);
```
createBrowserRouter : creates router object using HTML5 hsitory API , defines routes as an array of object

loader:  Get the data ready before rendering the component.Makes your page load faster and cleaner, without writing useEffect and useState.

RouterProvider: It's the component that renders the router created by createBrowserRouter
