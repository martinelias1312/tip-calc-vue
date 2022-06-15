<template>
  <div className="card-inputs">
    <section className="bill">
      <h2>Bill</h2>
      <input
        type="number"
        placeholder="0"
        v-model="bill"
        @input="dataChanged"
      />
    </section>

    <section className="tip">
      <h2>Select Tip %</h2>
      <div className="btn-grid">
        <button class="btn" value="5" @click="tipChanged">5%</button>
        <button class="btn" value="10" @click="tipChanged">10%</button>
        <button class="btn" value="15" @click="tipChanged">15%</button>
        <button class="btn" value="25" @click="tipChanged">25%</button>
        <button class="btn" value="50" @click="tipChanged">50%</button>
        <input
          type="number"
          className="btn-custom"
          placeholder="Custom"
          @input="tipChanged"
        />
      </div>
    </section>

    <section className="people">
      <h2>
        Number of People
        <p className="msg-zero" v-if="people === 0">Can´t be zero</p>
      </h2>
      <input
        type="number"
        placeholder="0"
        v-model="people"
        @input="dataChanged"
      />
    </section>
  </div>
</template>

<script>
// style
import "@/assets/scss/main.scss";
export default {
  data() {
    return {
      bill: null,
      people: null,
      tip: null,
      personTip: 0,
      personTotal: 0,
    };
  },
  methods: {
    tipChanged(e) {
      this.tip = e.target.value;
      this.dataChanged();

      //btn styling on click
      let tipBtns = document.querySelectorAll("button");
      tipBtns.forEach((btn) => btn.classList.remove("activeBtn"));
      if (e.target.className == "btn") {
        e.target.classList.add("activeBtn");
      }
    },
    dataChanged() {
      if (this.people !== null && this.bill !== null && this.people !== "") {
        this.personTip = (this.bill * (this.tip / 100)) / this.people;
        this.personTotal = this.bill / this.people + this.personTip;
      } else {
        this.personTip = 0;
        this.personTotal = 0;
      }
      this.$emit("personTip", this.personTip);
      this.$emit("personTotal", this.personTotal);
    },
  },
};
</script>
