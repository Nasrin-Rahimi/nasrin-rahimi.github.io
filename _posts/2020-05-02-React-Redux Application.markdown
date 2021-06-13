---
layout: post
title:      "React-Redux Application"
date:       2021-05-02 02:48:55 -0400
permalink:  React-Redux Application
---

I love Wegman's bakery and I'm ordering at least one time a month from their bakery. So for my React-Redux project I decided to wirte an application to have some bakery products. Customers are be able to login and see their orders. They can see bakery's categories and their products and should be able to order products.
 
 Creating Rails API Backend Application
 
    rails new best-cake-ever-backend --api
    
The Rails API should handle data persistence. I created models, routes, controllers and serializers in my backend before starting my frontend with React.
    
Creating React Frontend Application

    npx create-react-app best-cake-ever-frontend

The environment will have everything needed to build a single-page React app.

Running The Development Web Server

    $ npm run start
    or
    $ npm start
    
You can see application running on http://localhost:3000/.

Install redux and react-redux

    npm install redux react-redux
    or
    yarn add redux react-redux

react-redux lets us connect redux with our react application easily.

    import React from 'react';
    import ReactDOM from 'react-dom';
    import { Provider } from 'react-redux'
    import store from './store.js'
    import App from './App';
    
    ReactDOM.render(
     <Provider store={ store }> 
     <App /> 
     </Provider>, document.getElementById('root')
    );

Router
React Router allows us to build a single-page web application with navigation without the page refreshing as the user navigates. React Router uses component structure to call components, which display the appropriate information.
I added Router to index.js wrapping <APP/> child components.

Components
I used Functional components on components I didn't need state or lifecycle which are available to the class components.

Thanks for reading!
You can check my gems here:
(https://github.com/Nasrin-Rahimi/best-cake-ever-frontend),
(https://github.com/Nasrin-Rahimi/best-cake-ever-backend)



