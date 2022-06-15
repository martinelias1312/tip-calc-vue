<template>
  <div className="card-inputs">
    <section className="bill">
      <h2>Bill</h2>
      <input
        type="number"
        placeholder="0"
        v-model="bill"
        @input="valueChanged"
      />
    </section>

    <section className="tip">
      <h2>Select Tip %</h2>
      <div className="btn-grid">
        <button
          value="5"
          @click="
            valueChanged;
            tipChanged;
          "
        >
          5%
        </button>
        <button
          value="10"
          @click="
            valueChanged;
            tipChanged;
          "
        >
          10%
        </button>
        <button
          value="15"
          @click="
            valueChanged;
            tipChanged;
          "
        >
          15%
        </button>
        <button
          value="25"
          @click="
            valueChanged;
            tipChanged;
          "
        >
          25%
        </button>
        <button
          value="50"
          @click="
            valueChanged;
            tipChanged;
          "
        >
          50%
        </button>
        <input
          type="number"
          className="btn-custom"
          placeholder="Custom"
          @input="
            valueChanged;
            tipChanged;
          "
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
        @input="valueChanged"
      />{{ personTip }}||{{ personTotal }}
    </section>
  </div>
</template>

<script>
// style
import "@/assets/scss/main.scss";
export default {
  methods: {
    tipChanged(e) {
      this.tip = e.target.value;
      this.valueChanged();
    },
    valueChanged() {
      this.personTip = (this.bill * (this.tip / 100)) / this.people;
      this.personTotal = this.bill / this.people + this.personTip;
    },
  },
  data() {
    return {
      people: null,
      bill: null,
      tip: null,
      personTotal: 0,
      personTip: 0,
    };
  },
};
</script>
