<script setup>
  import Card from "./components/Card.vue"
  import Header from "./components/Header.vue"
</script>

<template>
  <Header />

  <div class="content">
    <Card :index="1" :label="'Test'" />
  </div>
</template>

<style scoped></style>
