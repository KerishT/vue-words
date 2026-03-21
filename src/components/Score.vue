<script setup>
  import IconHeart from "../assets/icons/IconHeart.vue"

  const { value } = defineProps({
    value: {
      type: Number,
      default: 0,
    },
  })
</script>

<template>
  <span class="score">
    <span>{{ value }}</span>
    <IconHeart />
  </span>
</template>

<style scoped>
  .score {
    display: inline-flex;
    gap: 6px;
    color: var(--blue);
    font-weight: 700;
    font-size: 16px;
    line-height: 24px;
    background-color: var(--blue-light);
    padding: 12px 24px;
    border-radius: 36px;
  }
</style>
