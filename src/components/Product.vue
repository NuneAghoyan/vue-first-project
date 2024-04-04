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
    name: {
      type: String,
      required: true
    },
    price: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    }
   }
  }
</script>

<template>
  <main>
   <div>
    <Name  :name="name" />
    <Price :price='price' />
    <Description :description='description' />
   </div>
  </main>
</template>

<style scoped>
 div{
  background-color: rgb(239, 228, 249);
  border: 2px solid blueviolet;
  border-radius: 5px;
  margin: 10px;
  padding: 5px;
    }
</style>
