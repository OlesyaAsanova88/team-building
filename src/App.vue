<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink class="link mx-5" to="/">Home</RouterLink>
        <RouterLink  class="link" to="/about">About</RouterLink>
      </nav>
    </div>
  </header>
  <RouterView />
</template>
<style scoped lang="scss">
.wrapper {
  font-family: "Prata", sans-serif;

  text-align: center;
  margin: 20px;
  box-shadow: 0 0 15px teal;
}
.link {
  text-decoration: none;
  font-size: 24px;
  color: teal;
}
.link:hover {
  color: rgb(39, 199, 151);
}
</style>
