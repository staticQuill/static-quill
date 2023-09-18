<script setup lang="ts">
defineProps<{
  msg: string
  submsg: string
}>()
</script>

<template>
  <div class="greetings">
    <h1>{{ msg }}</h1>
    <h2>{{ submsg }}</h2>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  text-decoration: none;
  color: var(--vt-c-electric);
  transition: 0.4s;
  text-align: center;
}

@media (prefers-color-scheme: light) {
  h1 {
    color: var(--vt-c-dark-electric);
  }
}

h2 {
  font-size: 1.1rem;
}

.greetings h1,
.greetings h2,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h2,
  .greetings h3 {
    text-align: left;
  }
}
</style>
