<template lang="pug">
#app
  Header
  Carousel
  Pane
  Pane
  Pane
  Footer
</template>

<script>
import '@/assets/css/reset.css'
import 'animate.css'

import Header from './views/Header'
import Carousel from './views/Carousel'
import Footer from './views/Footer'
import Pane from './views/Pane'

export default {
  name: 'App',
  components: {
    Header,
    Carousel,
    Footer,
    Pane
  }
}
</script>

<style>
</style>
