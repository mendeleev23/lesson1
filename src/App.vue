<template>
  <div id="app">
    <label> X = <input id="X" type="text" v-model.number="n1"></label><br>
    <label> Y = <input id="Y" type="text" v-model.number="n2"></label><br>
    <button v-on:click="Plus(n1,n2)">Сложение(X+Y) </button>
    <button v-on:click="Minus(n1,n2)">Вычитание(X-Y)</button>
    <button v-on:click="Multi(n1,n2)">Умножение(X*Y)</button>
    <button v-on:click="Divide(n1,n2)">Деление(X/Y)</button>
    <button v-on:click="Power(n1,n2)">Возведение в степень(X^Y)</button>
    <button v-on:click="IntDivide(n1,n2)">Целочисленное деление(X/Y   Без остатака)</button><br>
    <button v-for="item in From0to9" :key="item" v-on:click="Vvod(item,picked)">{{ item }}</button>
    <button v-on:click="Vvod(backspace,picked)"> {{ backspace }} </button>
    <form>
    <input type="radio" id="one" value="X" v-model="picked">
    <label for="one">X</label>
    <br>
    <input type="radio" id="two" value="Y" v-model="picked">
    <label for="two">Y</label>
    <br>
    <span>Выбрано: поле {{ picked }}</span>
    </form>
    <h1>{{ result }}</h1>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
      },
  data(){
    return{
      n1:0,
      n2:0,
      result:0,
      From0to9:[0,1,2,3,4,5,6,7,8,9],
      backspace:'<=',
      picked:0
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
    },
    VVod(vod,pole){
        if (pole == "X"){
          if(!isNaN(vod)){
          document.getElementById(pole).value=vod;
          this.n1 = vod;
        }
          else {this.n1=Math.trunc(this.n1/10);
          }
          return this.n1;
      }
        else if(pole == "Y"){
          if(!isNaN(vod)){
          document.getElementById(pole).value=vod;
          this.n2 = vod;
        }
          else {this.n2=Math.trunc(this.n2/10);
          }
        return this.n2;
      }
        else{
          return  alert("Выберите поле ввода!!");
      }
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
