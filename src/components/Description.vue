<script>
export default {
  props: {
    description: {
      type: String,
      required: true
    }
  }
}
</script>

<template>
 <h2>Fruit description: {{description}}</h2>
</template>


