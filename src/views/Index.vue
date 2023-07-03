<template>
  <section id="app">
    Enviroment: Development
    <Board></Board>
  </section>
</template>
<script>

import Board from "@/components/chart/Board.vue";
export default {
  name:"Main",
  components:{
    Board
  },
  data(){
    return{

    }
  },
}
</script>
<style lang="scss">
body{
  font-family: 'Lato', sans-serif;
  padding:0px 5px;
  margin:0 auto;
  box-sizing: border-box;
  .container{
    max-width: 1200px;
    margin:0 auto;
  }
}
</style>