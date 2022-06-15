<template>
  <div className="tip-summary">
    <div className="tip-person">
      <h2 className="tip-person-heading">Tip Amount<span>/ person</span></h2>
      <p className="tip-person-sum">${{ tip.toFixed(2) }}</p>
    </div>

    <div className="tip-total">
      <h2 className="tip-total-heading">Total<span>/ person</span></h2>
      <p className="tip-total-sum">${{ total.toFixed(2) }}</p>
    </div>
    <button class="btn-reset" :class="{ disabled: !isNumbers }">RESET</button>
  </div>
</template>

<script>
// style
import "@/assets/scss/main.scss";
export default {
  data() {
    return {
      isNumbers: false,
    };
  },
  props: {
    tip: {
      type: Number,
    },
    total: {
      type: Number,
    },
  },
};
</script>
