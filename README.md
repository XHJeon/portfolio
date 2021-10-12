## References

+ [Creating a Vue project using Vue CLI](https://cli.vuejs.org/guide/creating-a-project.html#vue-create)
+ [Installing vuetify using Vue CLI](https://vuetifyjs.com/en/getting-started/installation/)
+ [Installing vue-i18n using Vue CLI](https://kazupon.github.io/vue-i18n/installation.html)
+ [Adding the project to GitHub](https://docs.github.com/es/github/importing-your-projects-to-github/importing-source-code-to-github/adding-an-existing-project-to-github-using-the-command-line)
+ [Creating a fake online REST server](https://my-json-server.typicode.com/)
+ [Deploying from GitHub using Render](https://cli.vuejs.org/guide/deployment.html#general-guidelines)
    + [Connecting GitHub with Render](https://render.com/docs/github)
+ [Adding custom domains in Render](https://render.com/docs/custom-domains)
    + [Configuring domain with Sered and Cloudflare](https://sered.net/revista/configura-tu-dominio-con-sered-y-cloudflare)
    + [Configuring Cloudflare DNS](https://render.com/docs/configure-cloudflare-dns)


## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


## Creating the Project

### node_modules
Dependencies needed to build project

### public
Files you don't want to process through Webpack

### src
Application code
- assets: Store images, fonts, etc.
- components: Building blocks of the app
- Vue Router: App navigation
- Vuex: State Management
- views: Components for different "views" of app
- App.vue: Root component (All other components are nested within it)
- main.ts: Renders App and mounts it to DOM



## Single File Components

- template -> body 
- script -> brain
- style -> clothes


## Vue Router Essentials

### Server-Side Routing
The user types a url, the browser requests the url from the server, and the server returns the page.
If the user where to click on a link on that page, the browser would request that url, and return the new page.

Browser refreshes on every page load.

### Client-Side Routing
When the user types in the url, the browser is going to request that url, and the server returns page index.html
including the rest of the app.

Because the app already has all the code it needs within the browser, Vue, with the help of Vue Router, compares and
then renders the differences without ever reloading the page.


## API Calls with Axios
We don't want data to be hard-coded. We want to be fetching the data with and API Call where we make a request to our
server for the data, the server sends back a response with the data as JSON, and then we take data and set it to
display.

### Axios
- GET, POST, PUT, and DELETE requests
- Add authentication to each request
- Set timeouts if requests take too long
- Configure defaults for every request
- Intercept requests to create middleware
- Handle errors and cancel requests properly
- Properly serialize and deserialize requests & responses


## Deploying with Render
To consider for deployment:
- Find a web hosting service
- Get SSL for a secure domain
- Build the site locally
- Drop those files into the server
- Ensure its served correctly

Once deployed you have to maintain it, add features, fix bugs, a nd ensure emergency rollbacks.


## Receiving URL Parameters

Use a Route parameter as Props
```
{
    path: '/events/:page',
    component: Events,
    props: true
}

props: {
    page: Number
}
```

Props Object Mode
```
{
    path: '/',
    name: 'Home',
    component: Home,
    props: { show: true }
}

props: {
    show: Boolean
}
```

Props Function Mode
```
http://localhost:8080/?e=true

{
    path: '/',
    name: 'Home',
    component: Home,
    props: (route) => ({ show: route.query.e })
}

props: {
    show: Boolean
}
```
