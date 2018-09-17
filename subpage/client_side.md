
Frontend config details
=======================

   ![Settings Window](https://raw.github.com/Puneethkumarck/SpringProjects_Jhipster/master/screenshot/front_end.png)
   
   
  - <b>app:</b> This folder holds the Angular application's Typescript source code, which is organized with a folder per feature:
  
  - <b>app.main.ts:</b> This is the main file for the Angular app. This bootstraps the Angular application. Notice that it uses platformBrowserDynamic, which lets the application work with JIT (Just-in-time) compilation in the browser. This is ideal for development:
  
  ```
  platformBrowserDynamic().bootstrapModule(StoreAppModule)
   .then((success) => console.log(`Application started`))
   .catch((err) => console.error(err)); 
  ```
  
  - <b>app.module.ts:</b> This is the main module for the Angular app. It declares app level components and providers, and imports other modules for the application. It also bootstraps the main application component:
  
  ```
  @NgModule({
    imports: [
        BrowserModule,
        ...
        StoreEntityModule,
        // jhipster-needle-angular-add-module JHipster 
         will add new module here
    ],
    declarations: [
        JhiMainComponent,
        ...
        FooterComponent
    ],
    providers: [
        ProfileService,
        ...
        UserRouteAccessService
    ],
    bootstrap: [ JhiMainComponent ]
})
export class StoreAppModule {}
  
  ```
  
- <b>account:</b> This module consists of account-related features such as activate, password, password-reset, register, and settings. Each typical component consists of component.html, component.ts, route.ts, and service.ts files.

- <b>admin:</b> This module consists of admin-related features such as audits, configuration, docs, health, logs, metrics, tracker, and user-management. Each typical component consists of component.html, component.ts, route.ts, and service.ts files.

- <b>blocks:</b> This folder consists of HTTP interceptors and other configs used by the application.

- <b>entities:</b> This is where entity modules will be created.

- <b>home:</b> The homepage module.

- <b>layouts:</b> This folder has layout components like the navbar, footer, error pages, and so on.

- <b>shared:</b> This module contains all the shared services (auth, tracker, user), components (login, alert), entity models, and utilities required for the application.

- <b>content:</b> This folder contains static content like images, CSS, and SASS files.

- <b>i18n:</b> This is where the i18n JSON files live. Each language has a folder with numerous JSON files organized by modules.

- <b>swagger-ui:</b> This folder has the Swagger UI client used in development for API documentation.

- <b>index.html:</b> This is the web application's index file. This contains very minimal code for loading the angular application's main component. It is a single page Angular application. You will also find some commented out utility code like Google analytics script and Service worker scripts on this file. These can be enabled if required:

```
<!doctype html>
<html class="no-js" lang="en" dir="ltr">
<head>
    ...
</head>
<body>
    ...
    <jhi-main></jhi-main>
    <noscript>
        <h1>You must enable javascript to view this page.</h1>
    </noscript>
    ...
</body>
</html>
```
