<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <label> X = <input type="text" v-model.number="n1"></label><br>
    <label> Y = <input type="text" v-model.number="n2"></label><br>
    <button v-on:click="Plus(n1,n2)">Сложение(X+Y) </button>
    <button v-on:click="Minus(n1,n2)">Вычитание(X-Y)</button>
    <button v-on:click="Multi(n1,n2)">Умножение(X*Y)</button>
    <button v-on:click="Divide(n1,n2)">Деление(X/Y)</button>
    <button v-on:click="Power(n1,n2)">Возведение в степень(X^Y)</button>
    <button v-on:click="IntDivide(n1,n2)">Целочисленное деление(X/Y   Без остатака)</button>
    <h1>{{ result }}</h1>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return{
      n1:0,
      n2:0,
      result:0
    }
  },
  methods:{
    Plus(a,b){
      return this.result=a+b;
    },
    Minus(a,b){
      return this.result=a-b;
    },
    Multi(a,b){
      return this.result=a*b;
    },
    Divide(a,b){
      return this.result=a/b;
    },
    Power(a,b){
      return this.result=Math.pow(a,b);
    },
    IntDivide(a,b){
      return this.result=Math.trunc(a/b);
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
