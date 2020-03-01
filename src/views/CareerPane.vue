<template lang="pug">
div#careerPane
  div(id='careerPaneContainer' class='carousel slide carousel-fade' data-ride='carousel' data-pause='false')
    div.carousel-inner
      div(v-for="(item, index) in slidesImgList" :key="index" :class='index === 0 ? "carousel-item active" : "carousel-item" ')
        img(class='d-block w-100' :style="{backgroundImage: 'url(' + item + ')' }")
  div.careerPaneContent
    div.paneContentContainer
      div.paneContentTitle 創造世界
      div.paneContentSubtitle 了解暴雪的工作機會
      HomeButton(buttonData='探索職涯')
</template>

<script>
import HomeButton from '@/components/HomeButton'

const slides = [
  require('@/assets/image/careerPane/slide1.jpg'),
  require('@/assets/image/careerPane/slide2.jpg'),
  require('@/assets/image/careerPane/slide3.jpg'),
  require('@/assets/image/careerPane/slide4.jpg'),
  require('@/assets/image/careerPane/slide5.jpg')
]

export default {
  name: 'CareerPane',
  components: {
    HomeButton
  },
  data () {
    return {
      slidesImgList: slides
    }
  }
}
</script>

<style scoped>
#careerPane {
  position: relative;
}

#careerPaneContainer {
  height: 60vh;
  min-height: 420px;
}

.carousel-inner > .carousel-item{
  transition: opacity 3s ease-in-out !important;
  -webkit-transition: opacity 3s ease-in-out !important;
  -o-transition: opacity 3s ease-in-out !important;
}

.carousel-item > img {
  height: 60vh;
  min-height: 420px;
  background-position: center top;
  background-repeat: no-repeat;
  background-size: auto 100vh;
}

.careerPaneContent {
  z-index: 999;
  position: absolute;
  width: 100%;
  height: 60vh;
  min-height: 420px;
  top: 0;
  left: 0;
  padding: 120px 0;
}

.paneContentContainer {
  padding: 0 15vw;
}

.paneContentContainer {
  display: inline-flex;
  flex-direction: column;
  align-items: flex-start;
}

.paneContentTitle {
  color: #fff;
  font-weight: 400;
  font-size: 43.94px;
}

.paneContentSubtitle {
  color: rgba(255,255,255,0.8);
  font-size: 22.5px;
  padding-bottom: 40px;
}
</style>
