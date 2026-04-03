<script setup>
  import { ref } from "vue"
  import Card from "./components/Card.vue"
  import Header from "./components/Header.vue"

  const score = ref(10)
  const cardData = ref({
    index: 1,
    word: "Test",
    translation: "Тест",
    state: "opened",
    status: "success",
  })
</script>

<template>
  <Header :score />

  <div class="content">
    <Card v-bind="cardData" />
  </div>
</template>

<style scoped></style>
