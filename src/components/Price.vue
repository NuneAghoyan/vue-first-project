<script>
export default {
  props: {
    price: {
      type: String,
      required: true
    }
  }
}
</script>

<template>
 <h2>Fruit price: {{price}}</h2>
</template>


