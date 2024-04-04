<script>
export default {
  props: {
    name: {
      type: String,
      required: true
    }
  }
}
</script>

<template>
 <h2>Fruit name: {{name}}</h2>
</template>


