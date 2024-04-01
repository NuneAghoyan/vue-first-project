<script>
export default {
  data() {
    return {
      count: 0,
      amount: 0,
      currencyBtn: "USD -> AMD"
    };
  },

  methods: {
    handleInputChange(event) {
      this.count = event.target.value;
      if (this.currencyBtn === "AMD -> USD") {
        this.amount = this.count * 400;
      } else {
        this.amount = this.count / 400;
      }
    },
    changeCurrencyBtn() {
      this.count = 0;
      this.amount = 0;
      if (this.currencyBtn === "USD -> AMD") {
        this.currencyBtn = "AMD -> USD";
      } else {
        this.currencyBtn = "USD -> AMD";
      }
    },
    currencyChange() {
      return this.currencyBtn === "USD -> AMD"
    },
    inputClick(event) {
      this.count = this.count === 0 ? "" : event.target.value;
    }
  }
}
</script>

<template>
  <h4 v-if="currencyChange()">AMD -> USD</h4>
  <h4 v-else>USD -> AMD</h4>
  <input type="number" :value="count" @input="handleInputChange" @click="inputClick">
  <input type="number" :value="amount" disabled>
  <div><button @click="changeCurrencyBtn()">{{ currencyBtn }}</button></div>
</template>

<style scoped>
h4 {
  margin-left: 2px;
}

input {
  margin-right: 2px;
}
</style>
