<template lang="pug">
#app
  Header
  Carousel
  GameList
  News
  CareerPane
  Footer
</template>

<script>
import '@/assets/css/reset.css'
import 'animate.css'

import Header from './views/Header'
import Carousel from './views/Carousel'
import GameList from './views/GameList'
import News from './views/News'
import CareerPane from './views/CareerPane'
import Footer from './views/Footer'

export default {
  name: 'App',
  components: {
    Header,
    Carousel,
    GameList,
    News,
    CareerPane,
    Footer
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
