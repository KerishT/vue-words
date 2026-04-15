<script setup>
  import Card from "./Card.vue"

  defineProps({
    cards: {
      type: Array,
      default: () => [],
    },
  })
</script>

<template>
  <div class="cards">
    <Card v-for="card in cards" v-bind="card" :key="card.index" />
  </div>
</template>

<style scoped>
  .cards {
    display: flex;
    gap: 100px 60px;
    flex-wrap: wrap;
  }
</style>
