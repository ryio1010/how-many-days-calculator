<template>
  <form @submit.prevent="submitForm">
    <input type="text" v-model="title" placeholder="タイトル">
    <input type="date" v-model="baseDate" placeholder="日付">
    <input type="number" v-model="plusDays" placeholder="日後">
    <button type="submit">Check How Many Days!</button>
  </form>
</template>

<script setup lang="ts">
import {ref} from "vue";

const title = ref("");
const baseDate = ref("");
const plusDays = ref("");

const submitForm = () => {
  emits("submit-form", title.value, baseDate.value, plusDays.value);
};

const emits = defineEmits([
  "submit-form"
])

</script>

<style scoped>

</style>