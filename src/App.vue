<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="panel-left">
    <header>
      <div class="branding">
        <img alt="Static Quill logo" class="logo" src="@/assets/logo.svg" width="250" height="250" />
        <HelloWorld msg="Static Quill Limited" submsg="Clever Web Development & Friendly Software Solutions"/>
      </div>
    </header>
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/portfolio">Portfolio</RouterLink>
      <RouterLink to="/contact">Contact</RouterLink>
    </nav>
  </div>
  <RouterView />
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
}

nav {
  font-size: 12px;
  grid-column-start: 2;
  grid-column-end: 3;
  line-height: 100%;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

@media (min-width: 1024px) {
  .logo {
    margin: 0 20% 0 20%;
    place-items: center;
  }

  header {
    display: flex;
    place-items: center;
  }

  .branding {
    display: flex;
    place-items: center;
    flex-wrap: wrap;
  }

  nav {
    font-size: 1rem;
    text-align: right;
    padding-right: 2rem;
    margin-top: 10em;
  }

  nav a {
    margin-bottom: 1rem;
    margin-top: 1rem;
    display: block;
    width: 100%;
  }
}
</style>
