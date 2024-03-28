<script>
export default {
  data() {
    return {
      email: ""
    };
  },
  methods: {
    emailInput() {
      this.email = prompt("Enter your email:");
    },
    resetEmail() {
      this.email = "";
    },
    validateEmail(userEmail) {
      return /^[a-z0-9._-]+@[a-z]+\.[a-z]{2,4}$/.test(userEmail);
    }
  }
}
</script>

<template>
  <header>
  </header>

  <main>

    <button @click="emailInput()">Input Email</button>
    <button @click="resetEmail()">Reset</button>
    <div class="green-border" v-show="validateEmail(email)">
      <h1>{{ email }}</h1>
      <h4>The email is valid.</h4>
    </div>
    <div class="red-border" v-show="!validateEmail(email) && email">
      <h1>{{ email }}</h1>
      <h4>The email is invalid.</h4>
    </div>

    <!-- <div class="red-border" v-if="!validateEmail(email) && email">
      <h1>{{ email }}</h1>
      <h4>The email is invalid.</h4>
    </div>
    <div class="green-border" v-else-if="validateEmail(email) && email">
      <h1>{{ email }}</h1>
      <h4>The email is valid.</h4>
    </div> -->

  </main>

</template>

<style scoped>
.green-border {
  border: 2px solid green;
  padding: 6px;
  margin-top: 6px;
  border-radius: 8px;
}

.red-border {
  border: 2px solid red;
  padding: 6px;
  margin-top: 6px;
  border-radius: 8px;
}

button {
  margin-right: 10px;
}

header {
  line-height: 1.5;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
