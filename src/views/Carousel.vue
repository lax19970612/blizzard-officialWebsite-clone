<template lang="pug">
div#Carousel-container
  div(id='Carousel-body' class='carousel slide carousel-fade' data-ride='carousel')
    ol.carousel-indicators
      li(data-target='#Carousel-body' v-for='(image, index) in ImageList' :data-slide-to='index' :class='index === 0 ? "active" : ""')
    div.carousel-inner
      div(v-for='(image, index) in ImageList' :class='index === 0 ? "carousel-item active" : "carousel-item" ')
        img(class='d-block w-100' :style="{backgroundImage: 'url(' + image + ')' }")
        div.carousel-caption
          img(class='animated bounceInRight fast' :src='GameLogoList[index]')
          h3(class='animated bounceInRight fast') {{ CaptionTitle[index] }}
          div(class='button animated bounceInRight fast') {{ ButtonText[index] }}
    a(class='carousel-control-prev' href='#Carousel-body' role='button' data-slide='prev')
      span.carousel-control-prev-icon
    a(class='carousel-control-next' href='#Carousel-body' role='button' data-slide='next')
      span.carousel-control-next-icon
</template>

<script>
const ImageList = [require('../assets/image/carousel/slides1.png'),
  require('../assets/image/carousel/slides2.jpg'),
  require('../assets/image/carousel/slides3.jpg'),
  require('../assets/image/carousel/slides4.jpg'),
  require('../assets/image/carousel/slides5.jpg'),
  require('../assets/image/carousel/slides6.jpg')]

const GameLogoList = [require('../assets/image/gameLogo/game1.png'),
  require('../assets/image/gameLogo/game2.png'),
  require('../assets/image/gameLogo/game3.png'),
  require('../assets/image/gameLogo/game4.png'),
  require('../assets/image/gameLogo/game5.png'),
  require('../assets/image/gameLogo/game6.png')]

const CaptionTitle = ['盡情享受美好時光！', '增強你的遊戲體驗', '每個傳奇都有一個開始', '全新單人冒險篇章', '勇闖彼世', '重返黑暗']
const ButtonText = ['了解詳情', '購買決勝時刻點數', '立即購買', '立即購買', '立即購買', '了解詳情']

export default {
  name: 'Carousel',
  data () {
    return {
      ImageList: ImageList,
      GameLogoList: GameLogoList,
      CaptionTitle: CaptionTitle,
      ButtonText: ButtonText
    }
  }
}
</script>

<style scoped>
#Carousel-container{
  height: 80vh;
  min-height: 600px;
}
.carousel-indicators > li {
  width: 5vw;
  margin: 0.3vw;
  height: 6px;
}

.carousel-indicators > li.active {
  background-color: #00aeff;
}

.carousel-item > img {
  height: 80vh;
  background-position: center top;
  background-repeat: no-repeat;
  background-size: auto 100vh;
}

.carousel-caption {
  right: auto;
  bottom: auto;
  top: 0;
  display: flex;
  justify-content: space-around;
  align-items: flex-start;
  flex-direction: column;
  height: 100%;
  padding: 100px 0;
}

.carousel-caption > img {
  width: 260px;
  height: auto;
}

.carousel-caption > h3 {
  font-size: 68.67px;
  animation-delay: 0.5s;
}

.carousel-caption > .button {
  border: 1px solid #00aeff;
  background-color: #0e86ca;
  color: #fff;
  font-size: 18px;
  font-weight: 400;
  padding: 10px 50px;
  text-decoration: none;
  text-align: center;
  cursor: pointer;
  animation-delay: 1s;
}
</style>
