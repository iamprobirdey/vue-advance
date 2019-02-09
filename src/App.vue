<template>
  <div id="app">
    <Header></Header>

    <HelloWorld msg="Welcome to Your Vue.js App">
      <h2 slot="app">I am from App.vue</h2>
      <span slot="learn">I just learned using slot</span>
    </HelloWorld>
    <img alt="Vue logo" src="./assets/logo.png">
    <hr>
    <hr>

    <component v-bind:is="comp"></component>
    <button @click="comp = 'samrat'">Switching Component</button>
    <button @click="comp = 'probir'">Switching Component</button>


    <Footer></Footer>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";
import Probir from "./components/ProbirDey.vue";
import Samrat from "./components/Samrat.vue";
import Footer from "./components/Footer.vue";



export default {
  name: "app",
  data() {
    return {
      comp : 'probir'
    }
  },
  components: {
    HelloWorld,
    Header,
    Footer,
    'probir':Probir,
    'samrat':Samrat
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
