<template>
  <div class="wrapper">
    <div class="container">
      <AppTitle/>
      <CalculatorForm @submit-form="calculateHowManyDays"/>
      <CalculateResult :calculateResults="calculateResults"/>
    </div>
  </div>

</template>

<script setup lang="ts">
import AppTitle from "@/components/AppTitle.vue";
import CalculatorForm from "@/components/CalculatorForm.vue";
import CalculateResult from "@/components/CalculateResult.vue";
import {reactive} from "vue";
import "./assets/base.css"

const calculateResults = reactive({
  calculateTitle: "",
  baseDate: "",
  plusDays: "",
  calculatedDate: "",
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

  const baseDate: Date = new Date(baseDateString);
  const plusDays: number = parseInt(plusDaysString);
  baseDate.setDate(baseDate.getDate() + plusDays);

  calculateResults.calculateTitle = title;
  calculateResults.baseDate = baseDateString;
  calculateResults.plusDays = plusDaysString;
  calculateResults.calculatedDate = baseDate.toISOString().split("T")[0];
  calculateResults.content = `${baseDateString}の${plusDaysString}日後は${calculateResults.calculatedDate}です`;
};
</script>