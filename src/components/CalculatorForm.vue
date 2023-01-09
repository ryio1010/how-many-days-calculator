<template>
  <form @submit.prevent="submitForm">
    <div>
      <input type="text" class="form_title form_component" v-model="title" placeholder="タイトル">
    </div>
    <div>
      <input type="date" class="form_baseDate form_component" v-model="baseDate" placeholder="日付">
      <input type="number" class="form_plusDays form_component" v-model="plusDays" placeholder="日後">
    </div>
    <div>
      <button type="submit">Check How Many Days!</button>
    </div>
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