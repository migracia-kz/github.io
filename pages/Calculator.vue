<template>
  <DatePicker
      style="width: 100vw;"
      v-model="date"
      mode="date"
  />
  <DatePicker
      style="width: 100vw;"
      v-model="date2"
      mode="date"
  />
  <p style="padding: 1rem 1rem">Разница между датами: <strong>{{ days }}</strong></p>
</template>

<script setup lang="ts">
const date = ref(new Date());
const date2 = ref(new Date());

const days = computed(() => {
  const oneDay = 24 * 60 * 60 * 1000; // Количество миллисекунд в одном дне
  const diffInTime = date2.value.getTime() - date.value.getTime();
  return Math.round(diffInTime / oneDay);
});
</script>