<template>
  <main className="tip-card">
    <CardInputs
      @personTip="personTip = $event"
      @personTotal="personTotal = $event"
      @resetActive="reset = $event"
      :reseting="reseting"
    />
    <TipSummary
      :tip="personTip"
      :total="personTotal"
      :resetActive="reset"
      @reseting="reseting = $event"
    />
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
      reset: false,
      reseting: false,
    };
  },
};
</script>
