<script setup>
  import Score from "./Score.vue"

  const { score } = defineProps({
    score: {
      type: Number,
      default: 0,
    },
  })
</script>

<template>
  <header class="header">
    <span class="logo">Запомни слово</span>

    <Score :value="score" />
  </header>
</template>

<style scoped>
  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 24px;
    padding: 30px 40px;
  }

  .logo {
    font-size: 16px;
    line-height: 24px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
  }
</style>
