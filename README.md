# vuejsrouter
 
 ## Vue Router is the official library for page navigation in Vue application

###  command 'vue add router' will add a build setup with pre-compiled .vue files for page navigation.

#### A folder named views is created for us along with two files About.vue and Home.vue. These files represent our pages.

#### A file named router/index.js file is also generated, which contains the router configurations.

### router/index.js
<br>
In this file we will import createRouter and createWebHistory from the vue-router library and will import the pages for router from the views folder.
The file  will conatin an array of objects named routes.This array represents our routes in the application

##### ROUTER OBJECTS

const routes = 
[
  {
  path: '/',
  name:'Home',
  component: Home
  },

    {
  path: '/about',
  name:'About',
  component: ABOUT
  }  

]

###  createRouter( options ): 
 Creates a Router instance that can be used by a Vue app.
 <br>
 In the index.js js after declaring routes ,add 
 <br>
 const router = createRouter({
  history: createWebHistory(process.env.BASE_URL),
  routes
})
### In the App.vue (root file), add router-link and router-view

######   <router-link to="/">Home</router-link> |  <router-link to="/about">About</router-link> <br>
        <router-view/>
        
####  Router-link tags.<br> 
These tags are just fancy anchor links. However unlike an anchor link 'a href=""', tag the 'router-link' will not reload the whole page. Remember Vue is a single-page application. The data for the app is already downloaded from the server. When we route to another view the application just hides some information and displays the requested information. router-link tags have a to property which refers to which page to visit. The <router-view/> tag is what renders the right component when navigation links are triggered.
        
#### In the index.js file add , use(router).mount(#app)
