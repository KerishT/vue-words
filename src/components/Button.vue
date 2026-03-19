<script setup></script>

<template>
  <button class="button">
    <slot />
  </button>
</template>

<style scoped>
  .button {
    border: none;
    border-radius: 100px;
    background: var(--blue);
    padding: 16px 10px;
    min-width: 335px;
    font-family: var(--font);
    font-size: 24px;
    line-height: 36px;
    font-weight: 400;
    color: var(--white);
    cursor: pointer;
  }

  .button:hover {
    background: var(--blue-dark);
  }
</style>
