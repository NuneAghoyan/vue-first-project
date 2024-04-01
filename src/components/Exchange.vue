<script>
export default {
  data() {
    return {
      count: 0,
      amount: 0,
      currencyText: "AMD -> USD",
      currencyBtn: "USD -> AMD"
    };
  },

  methods: {
    handleInputChange(event) {
      this.count = event.target.value;
      if (this.currencyText === "USD -> AMD") {
        this.amount = this.count * 400;
      } else {
        this.amount = this.count / 400;
      }
    },

    currencyChange() {
      const amd = "AMD -> USD";
      const usd = "USD -> AMD";

      if (this.currencyBtn === usd) {
        this.currencyBtn = amd;
        this.currencyText = usd;

      } else {
        this.currencyText = amd;
        this.currencyBtn = usd;
      }

      let count = this.count;
      this.count = this.amount;
      this.amount = count;

      // this.count = 0;
      // this.amount = 0;
    },

    // inputClick(event) {
    //   this.count = this.count === 0 ? "" : event.target.value;
    // }
  }
}
</script>

<template>
  <h4>{{ currencyText }}</h4>
  <input type="number" :value="count" @input="handleInputChange" @click="inputClick">
  <input type="number" :value="amount" disabled>
  <div><button @click="currencyChange">{{ currencyBtn }}</button></div>
</template>

<style scoped>
h4 {
  margin-left: 2px;
}

input {
  margin-right: 2px;
}
</style>
