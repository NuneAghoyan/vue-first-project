<script>
export default {
  props: {
    value: {
      type: String,
      required: true
    }
  }
}
</script>

<template>
 <h2>Fruit name: {{value}}</h2>
</template>


