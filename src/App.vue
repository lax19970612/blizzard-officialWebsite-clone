<template lang="pug">
#app
  Header
  Carousel
  GameList
  News
  Pane
  Footer
</template>

<script>
import '@/assets/css/reset.css'
import 'animate.css'

import Header from './views/Header'
import Carousel from './views/Carousel'
import GameList from './views/GameList'
import News from './views/News'
import Footer from './views/Footer'
import Pane from './views/Pane'

export default {
  name: 'App',
  components: {
    Header,
    Carousel,
    GameList,
    News,
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
