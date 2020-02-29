<template lang='pug'>
  div {{ text }}
</template>

<script>
export default {
  name: 'HomeButton',
  props: { buttonData: String },
  data () {
    return {
      text: this.buttonData
    }
  }
}
</script>

<style scoped>
div {
  border: 1px solid #00aeff;
  background-color: #0e86ca;
  color: #fff;
  font-size: 18px;
  font-weight: 400;
  padding: 10px 50px;
  text-decoration: none;
  text-align: center;
  cursor: pointer;
}

div:hover {
  background-color: #00aeff;
}
</style>
