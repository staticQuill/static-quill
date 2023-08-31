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
  color: rgb(0, 121, 204);
  transition: 0.4s;
  text-align: center;
}

h3 {
  font-size: 1.2rem;
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
