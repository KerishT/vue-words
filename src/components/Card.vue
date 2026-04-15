<script setup>
  import IconTick from "../assets/icons/IconTick.vue"
  import IconClose from "../assets/icons/IconClose.vue"

  const { index, word } = defineProps({
    index: {
      type: Number,
    },
    word: {
      type: String,
    },
    translation: {
      type: String,
    },
    state: {
      type: String,
    },
    status: {
      type: String,
    },
  })

  const emit = defineEmits(["revert", "changeStatus"])

  const onRevert = () => {
    emit("revert")
    emit("changeStatus")
  }
</script>

<template>
  <article class="card" @click="onRevert">
    <div class="content">
      <span class="index">{{ index }}</span>
      <span class="status">
        <IconTick v-if="status === 'success'" />
        <IconClose v-if="status === 'error'" />
      </span>

      <span class="word">{{ word }}</span>

      <span class="action">
        <span v-if="state !== 'opened'">{{
          status === "success" || status === "error"
            ? "Завершить"
            : "Перевернуть"
        }}</span>
        <div v-else class="statuses">
          <IconClose />
          <IconTick />
        </div>
      </span>
    </div>
  </article>
</template>

<style scoped>
  .card {
    padding: 30px 15px;
    background-color: var(--white);
    box-shadow: 0 0 16px 0 rgba(0, 0, 0, 0.1);
    border-radius: 16px;
    width: 250px;
    height: 370px;
    cursor: pointer;
  }

  .card:hover {
    box-shadow: 0 0 22px 0 rgba(0, 0, 0, 0.15);
  }

  .content {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    border: 1px solid #cce8ff;
    border-radius: 12px;
    height: 100%;
  }

  .index {
    position: absolute;
    left: 20px;
    top: -8px;
    font-size: 14px;
  }

  .status {
    position: absolute;
    left: 50%;
    top: -24px;
    transform: translateX(-50%);
  }

  .status svg {
    width: 48px;
    height: 48px;
  }

  .word {
    font-size: 18px;
  }

  .action {
    position: absolute;
    left: 50%;
    bottom: -12px;
    transform: translateX(-50%);
    display: flex;
    align-items: center;
    height: 24px;
    padding: 0 6px;
    background-color: var(--white);
    font-weight: 700;
    font-size: 12px;
    letter-spacing: 0.12em;
    color: #222;
    text-transform: uppercase;
  }

  .statuses {
    display: flex;
    gap: 30px;
  }
</style>
