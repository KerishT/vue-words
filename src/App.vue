<script setup>
  import { ref } from "vue"
  import Cards from "./components/Cards.vue"
  import Header from "./components/Header.vue"

  const score = ref(10)
  const cards = ref([
    {
      index: 1,
      word: "Test",
      translation: "Тест",
      state: "closed",
      status: "pending",
    },
    {
      index: 2,
      word: "Test",
      translation: "Тест",
      state: "opened",
      status: "pending",
    },
    {
      index: 3,
      word: "Test",
      translation: "Тест",
      state: "closed",
      status: "success",
    },
    {
      index: 4,
      word: "Test",
      translation: "Тест",
      state: "closed",
      status: "error",
    },
  ])
</script>

<template>
  <Header :score />

  <main class="content">
    <Cards :cards="cards" />
  </main>
</template>

<style scoped>
  .content {
    padding: 0 30px 40px 30px;
  }
</style>
