<script>
export default {
  props: {
    value: {
      type: String,
      required: true
    }
  },
  methods: {

    onChange() {
      if (this.value[this.value.length - 1] === "$") {
        this.value = parseFloat(this.value) * 400 + "֏";
      } else {
        this.value = parseFloat(this.value) / 400 + "$";
      }
      this.$emit('changeCurrency', this.value);
    }
  }
}
</script>

<template>
  <h2>Fruit price: {{ value }} </h2> <button @click="onChange"> Change the currency</button>
</template>

<style scoped>
h2 {
  display: inline;
}
</style>
