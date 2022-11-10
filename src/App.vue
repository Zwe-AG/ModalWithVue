<template>
  <div v-if="showModal">
    <HelloWorld  :header="header" :content="content" :theme="theme" @close="showModal=false"/>
  </div>
  <div v-if="showModalTwo">
    <HelloWorld  :header="headerTwo" :content="contentTwo" :theme="themeTwo" @close="showModalTwo=false"/>
  </div>
  <button @click="openModal">Open Modal</button>
  <button @click="openModalTwo">Open Modal Two</button>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      header : "Login Success",
      content : "Yo can go to anywhere from my app!!!",
      theme : 'success',
      headerTwo : "Login Failed",
      contentTwo : "Try Again You can use this app!!!",
      themeTwo : 'fail',
      showModal : false,
      showModalTwo : false
    }
  },
  methods: {
    openModal(){
      this.showModal = true
    },
    openModalTwo(){
      this.showModalTwo = true
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button{
  padding:10px 20px;
  background-color: black;
  color:white;
  border-radius:7%;
  border:none;
  margin-right:10px
}
button:nth-of-type(2){
  background-color: red;
}
</style>
