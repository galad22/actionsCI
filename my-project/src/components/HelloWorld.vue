<template>
  <div class="hello">
    <div class="teclado">
      <button v-for="number in numbers" @click="verNumeroClicat(number)" :key="number">{{ number }}</button>
    </div>
    <div v-if="numClicat !== null">
      <p>Has clicado en el número:  {{ numClicat }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      numClicat: null
    };
  },
  methods: {
    verNumeroClicat(number) {
      this.numClicat = number;
    }
  }
}
</script>

<style scoped>
.hello {
  text-align: center;
}

.teclado {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 10px;
}

.teclado button {
  padding: 15px;
  font-size: 18px;
  border: 1px solid #ccc;
  background-color: #f9f9f9;
  cursor: pointer;
}

.teclado button:hover {
  background-color: #e0e0e0;
}

.teclado button:active {
  background-color: #ccc;
}
</style>
