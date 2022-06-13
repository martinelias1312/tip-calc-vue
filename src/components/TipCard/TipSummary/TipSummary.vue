<template>
  <div className="tip-summary">
    <div className="tip-person">
      <h2 className="tip-person-heading">Tip Amount<span>/ person</span></h2>
      <p className="tip-person-sum">$0.00</p>
    </div>

    <div className="tip-total">
      <h2 className="tip-total-heading">Total<span>/ person</span></h2>
      <p className="tip-total-sum">$0.00</p>
    </div>
    <button className="btn-reset" disabled>RESET</button>
  </div>
</template>

<script>
// style
import "@/assets/scss/main.scss";
export default {};
</script>
