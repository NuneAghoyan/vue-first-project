<script>
import Name from './Name.vue';
import Price from './Price.vue';
import Description from './Description.vue';
export default {
  components: {
    Name,
    Price,
    Description
  },
  props: {
    fruit: {
      type: Object,
      required: true
    },
    // index: {
    //   type: Number,
    //   required: true
    // }
  },
  methods: {
    onChange(price) {
      this.fruit.price = price;
      this.$emit('changeCurrency', price);

    },
  }
}
</script>

<template>
  <main>
    <div>
      <Name :value="fruit.name" />
      <Price :value="fruit.price" @changeCurrency="onChange" />
      <Description :value="fruit.description" />
    </div>
  </main>
</template>

<style scoped>
div {
  background-color: rgb(239, 228, 249);
  border: 2px solid blueviolet;
  border-radius: 5px;
  margin: 10px;
  padding: 5px;
}
</style>
