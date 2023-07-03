<template>
  <button @click="clicked" :class="customClass ? customClass : ''">
    {{innerText}}
  </button>
</template>

<script>
export default {
  props:{
    innerText:String,
    customClass:String,
  },
  methods:{
    clicked(button){
      this.$emit("buttonClicks", button);
    }
  }
}
</script>

<style lang="scss" scoped>
button{
  padding:10px;
  background: #fd4370;
  border:none;
  color:#fff;
}
</style>