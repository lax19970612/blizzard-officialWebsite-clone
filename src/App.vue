<template lang="pug">
#app
  Header
  Carousel
  GameList
  Pane
  Pane
  Footer
</template>

<script>
import '@/assets/css/reset.css'
import 'animate.css'

import Header from './views/Header'
import Carousel from './views/Carousel'
import GameList from './views/GameList'
import Footer from './views/Footer'
import Pane from './views/Pane'

export default {
  name: 'App',
  components: {
    Header,
    Carousel,
    GameList,
    Footer,
    Pane
  }
}
</script>

<style>
body {
  box-sizing: border-box;
  background-color: #002650;
  color: #fff;
  font-size: 16px;
  line-height: 1.7;
  letter-spacing: 2px;
}
</style>
