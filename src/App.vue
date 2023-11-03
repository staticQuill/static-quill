<script setup lang="ts">
import {RouterLink, RouterView, useRoute} from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import { computed } from "vue";
import router from "@/router";


const isHome = computed(() => {
  const route = useRoute();
  console.log(route)
  return route.path == "/";
})
</script>

<template>
  <div class="panel-left">
    <header>
      <div v-bind:class="(isHome)?'router-inactive':'router-active'" class="branding">
        <img alt="Static Quill logo" class="logo" src="@/assets/logo.svg" />
        <HelloWorld msg="Static Quill Limited" submsg="Clever Web Development & Friendly Software Solutions"/>
      </div>
    </header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/portfolio">Portfolio</RouterLink>
      <RouterLink to="/contact">Contact</RouterLink>
    </nav>
  </div>

  <div class="panel-right">
    <RouterView />
  </div>
</template>

<style scoped>

header {
  line-height: 1.5;
  max-height: 100vh;
  grid-column-start: 1;
  grid-column-end: 2;
}

.panel-left {
  position: fixed;
  padding-top: 10vh;

  display: grid;
  align-content: center;
  grid-template-columns: 80% 20%;
  height: 100vh;
  width: 30vw;

  border-style: solid;
  border-width: 0;
  border-color: var(--vt-c-electric);
  border-right-width: medium;
  padding-bottom: 10em;
  border-image: url("@/assets/static-quill-border-image-darkmode.png") 1 6 5 0 repeat repeat;
}

@media (prefers-color-scheme: light) {
  .panel-left {
    border-image: url("@/assets/static-quill-border-image.png") 1 6 5 0 repeat repeat;
  }
}

.logo {
  place-items: center;
  margin: 0 auto 2rem;
  width: 20vw;
}

nav {
  font-size: 18px;
  grid-column-start: 2;
  grid-column-end: 3;
  display: block;
  height: 50vh;
}

nav a {
  display: block;
  width: 100%;
  margin-top: 2em;
  margin-bottom: 2em;
  padding-top: 2em;
  padding-bottom: 2em;
  text-align: center;
  border-radius: 10% 10% 10% 10%;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

.panel-right {
  padding-right: 1em;
  padding-left: 1em;
  top: 50%;
  transform: translateY(-50%);
  font-size: 1.5em;
}

@media (hover: hover) {
  nav a:hover {
    border-radius: 50% 50% 50% 50%;
  }
}


@media (max-width: 1024px) {
  .logo {
    align-items: center;
    margin: 0;
    width: 500px;
  }

  header {
    display: flex;
    place-items: center;
  }

  .branding {
    display: block;
    width: 80vw;
    text-align: center;
  }

  nav {
    position: absolute;
    font-size: 1rem;
    text-align: center;
    display: flex;
    left: 50%;
    transform: translateX(-50%);
    height: 2em;
  }

  nav a {
    display: flex;
    width: auto;
    padding-top: 0;
    padding-left: 1em;
    padding-right: 1em;
    border-radius: 50% 50% 20% 20%;
  }

  .panel-left {
    position: relative;
    display: block;
    align-content: center;
    width: 80vw;
    padding-top: 0;
    border: none;
  }

  .panel-right {
    position: absolute;
    width: 100%;
    padding-right: 1em;
    padding-left: 1em;
    left: 50%;
    top: 10em;
    transform: translateX(-50%);
  }

  .router-active {
    display: none;
    height: 0;
  }
}
</style>
