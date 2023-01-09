<template>
  <h2 class="result-title" v-if="calculateResults">{{ calculateResults.calculateTitle }}</h2>
  <div v-if="calculateResults">
    <p class="result-content">
      <span class="result-component">{{ calculateResults.baseDate }}</span>
      <span>の</span>
      <span class="result-component">{{ calculateResults.plusDays }}</span>
      <span>日後は</span>
      <span class="result-component">{{ calculateResults.calculatedDate }}</span>
      <span>です！！</span>
    </p>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  calculateResults: Object
});
</script>