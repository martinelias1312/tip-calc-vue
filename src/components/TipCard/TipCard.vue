<template>
  <main className="tip-card">
    <CardInputs />
    <TipSummary />
  </main>
</template>

<script>
import "@/assets/scss/main.scss";
import CardInputs from "./CardInputs/CardInputs.vue";
import TipSummary from "./TipSummary/TipSummary.vue";
export default {
  components: {
    CardInputs,
    TipSummary,
  },
};
</script>
