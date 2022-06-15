<template>
  <main className="tip-card">
    <CardInputs
      @personTip="personTip = $event"
      @personTotal="personTotal = $event"
    />
    <TipSummary :tip="personTip" :total="personTotal" />
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
  data() {
    return {
      personTip: 0,
      personTotal: 0,
    };
  },
};
</script>
