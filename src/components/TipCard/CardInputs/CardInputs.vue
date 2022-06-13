<template>
  <div className="card-inputs">
    <section className="bill">
      <h2>Bill</h2>
      <input
        type="text"
        placeholder="0"
        onChange="{handleInput}"
        ref="{billInput}"
      />
    </section>

    <section className="tip">
      <h2>Select Tip %</h2>
      <div className="btn-grid">
        <button onClick="{handleClick}">5%</button>
        <button onClick="{handleClick}">10%</button>
        <button onClick="{handleClick}">15%</button>
        <button onClick="{handleClick}">25%</button>
        <button onClick="{handleClick}">50%</button>
        <input
          className="btn-custom"
          placeholder="Custom"
          onChange="{handleInput}"
          ref="{customInput}"
          onClick="{handleClick}"
        />
      </div>
    </section>

    <section className="people">
      <h2>
        Number of People
        <p className="msg-zero display">Can´t be zero</p>
      </h2>
      <input
        type="text"
        placeholder="0"
        onChange="{handleInput}"
        ref="{peopleInput}"
      />
    </section>
  </div>
</template>

<script>
// style
import "@/assets/scss/main.scss";
export default {};
</script>
