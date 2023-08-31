<template>
  <div class="about">
    <h1>Public Projects: </h1>
    <ul>
      <li class="mainlist">
        <a href="https://www.convergent.beauty">Convergent Beauty:</a> An accessible database of beauty products and their sensory qualities.
        <br>
        <a href="https://www.youtube.com/watch?v=I9y5m0yYvS4">Watch a silent demo of the project</a>
        <br>
        Technologies Used:
        <ul>
          <li>Python with the Django Rest Framework for the backend </li>
          <li>Vue.js for the frontend</li>
          <li>PostgresQL for the relational data</li>
          <li>Elasticsearch for speedy data access</li>
        </ul>
      </li>
      <li class="mainlist">
        Pomodora: A pomodoro timer for Atlassian's Jira.
        <br>
        <a href="https://www.youtube.com/watch?v=VjjLNfFdJCE">View the video demo here</a>
        <br>
        <a href="https://staticquill.github.io/pomodora-docs/#/">Read the docs here</a>
        <br>
        Technologies Used:
        <ul>
          <li>React-like framework for Atlassian Projects (Atlassian Forge)</li>
          <li>GitHub Pages (for the docs)</li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

.mainlist {
  margin-top: 2em;
}
</style>
<script setup lang="ts">
</script>
