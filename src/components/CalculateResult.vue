<template>
  <h2>計算結果</h2>
  <h3 v-if="calculateResults">{{ calculateResults.calculateTitle }}</h3>
  <div v-if="calculateResults">
    <p>{{ calculateResults.content }}</p>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  calculateResults: Object
});
</script>