<template lang='pug'>
  div {{ buttonData }}
</template>

<script>
export default {
  name: 'HomeSmallButton',
  props: { buttonData: String }
}
</script>

<style scoped>
div {
  border: 1px solid #00aeff;
  background-color: #0e86ca;
  color: #fff;
  font-size: 15px;
  font-weight: 400;
  padding: 7px 42px;
  text-decoration: none;
  text-align: center;
  cursor: pointer;
}

div:hover {
  background-color: #00aeff;
}
</style>
