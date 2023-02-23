<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import logo from './components/logo.vue'
</script>

<template>
  <header class=" justify-center bg-lime-500">
    
      <div><logo class="w-72"></logo></div>
      
    
    
    
    
  </header>
  <!-- <RouterLink to="/"></RouterLink>
  <RouterLink to="/about"></RouterLink> -->

  <body class="mt-5 mr-3 ml-3 ">
    <div class="justify-between flex ">
      <div class="w-28 hover:-translate-y-1 hover:scale-105" >
        <button class=""><RouterLink to="/">
        <img class="rounded-lg mb-3 " src='./assets/inicio.png' alt="">
        </RouterLink>
      </button>
      </div>
      

      <div class="w-52 hover:-translate-y-1 hover:scale-105">
        <button><RouterLink to="/personajes">
        <img class="rounded-lg mb-3 " src='./assets/personajes.png' alt="">
        </RouterLink>
      </button> 
      </div>
       
      
      <div class="w-40 hover:-translate-y-1 hover:scale-105">
        <button><RouterLink to="/about">
        <img class="rounded-lg mb-3 " src='./assets/acercade.png' alt="">
        </RouterLink>
      </button>
      </div>
      

    </div>
    <nav>

    </nav>
  </body>
  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
