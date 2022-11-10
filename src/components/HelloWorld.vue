<template>
  <div class="backdrop" @click.self="hideModal">
    <div class="modal" :class="{success:theme==='success',delete:theme==='fail'}">
      <h1>{{ header }}</h1>
      <p>{{ content }}</p>
    </div>
  </div>
</template>

<script>
  export default {
    props :['header','content','theme'],
    methods: {
      hideModal(){
        this.$emit('close')
      }
    },
  }
</script>

<style scoped>
.backdrop{
  position: fixed;
  top:0;
  background-color: rgba(0,0,0,0.5);
  width:100%;
  height:100%;
}
.modal{
  width:400px;
  padding: 20px;
  margin: 100px auto;
  background-color: white;
  border-radius: 3%;
}
.success{
  background-color: greenyellow;
}
.delete{
  background-color: crimson;
}
</style>

