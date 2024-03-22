<script setup>
import HelloWorld from './components/HelloWorld.vue';
import TheWelcome from './components/TheWelcome.vue';
import { ref } from 'vue';

let count = ref(0);
function operation(operator) {
  switch (operator) {
    case 'minus10': count.value -= 10;
      break;
    case 'minus': count.value--;
      break;
    case 'plus': count.value++;
      break;
    case 'plus10': count.value += 10;
      break;
    case 'reset': count.value = 0;
      break;
    // default: "";
  }
}

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <button @click="operation('minus10')">-10</button>
    <button @click="operation('minus')">-</button>
    <span> {{ count }}</span>
    <button @click="operation('plus')">+</button>
    <button @click="operation('plus10')">+10</button>
    <button @click="operation('reset')">Reset</button>

    <!-- <TheWelcome /> -->
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
