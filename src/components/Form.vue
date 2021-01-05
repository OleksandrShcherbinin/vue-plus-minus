<template>
  <div class="main">
    <div class="plus-minus">
      <button class="plus-minus__button" v-on:click="increment"></button>
      <form class="plus-minus-form">
        <input class="plus-minus-form__input" type="number" placeholder="Введите число" required v-on:focusout="getNumber">
      </form>
      <button class="plus-minus__button" v-on:click="decrement"></button>
    </div>
    <div class="result">
      <p>{{number}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {number: ''}
  },
  methods: {
    getNumber(event) {
      this.number = event.target.value
      event.target.value = ''
    },
    increment() {
      this.number++
    },
    decrement() {
      this.number--
    }
  }
}
</script>

<style scoped lang="scss">
.plus-minus {
  margin: 0 auto;
  max-width: 600px;
  max-height: 600px;
  display: flex;
  &__button {
    width: 70px;
    cursor: pointer;
    border-radius: 50px;
    border: none;
    padding: 0;
  }
  &__button:focus {
    outline: none;
  }
  &__button:active {
    opacity: 0.5;
  }
  &__button:first-child {
    background: center / cover url("../assets/plus.png");
  }
  &__button:last-child {
    background: center / cover url("../assets/minus.png");
  }
  &-form {
    margin: 0 50px;
    &__input {
      height: 50px;
      padding: 5px;
      font-size: 30px;
    }
  }
}
.result {
  margin-top: 20px;
  font-size: 50px;
  font-weight: bold;
}

</style>