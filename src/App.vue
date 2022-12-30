<template>
  <AppTitle/>
  <CalculatorForm @submit-form="calculateHowManyDays"/>
  <CalculateResult :calculateResults="calculateResults"/>
</template>

<script setup lang="ts">
import AppTitle from "@/components/AppTitle.vue";
import CalculatorForm from "@/components/CalculatorForm.vue";
import CalculateResult from "@/components/CalculateResult.vue";
import {reactive} from "vue";

const calculateResults = reactive({
  calculateTitle: "",
  content: "",
});

const calculateHowManyDays = (
    title: string,
    baseDateString: string,
    plusDaysString: string
) => {
  if (!title || !baseDateString || !plusDaysString) {
    return;
  }

  const baseDate = new Date(baseDateString);
  const plusDays = parseInt(plusDaysString);
  baseDate.setDate(baseDate.getDate() + plusDays);

  calculateResults.calculateTitle = title;
  calculateResults.content = `${baseDateString}の${plusDaysString}日後は${baseDate.toLocaleDateString()}です！`
};
</script>