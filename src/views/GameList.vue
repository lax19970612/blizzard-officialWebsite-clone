<template lang='pug'>
div#gameListContent
  div.gameListContainer
    PaneTitle(HeadingText='遊戲' HeadingSubtext='所有遊戲')
    div.gameListRow
      h3.gameCellTitle 暴雪
      div.gameListGalleryContainer
        div.gameListGalleryInner
          GameGalleryItem(v-for="(item, index) in gameGalleryItemData" :key='index' :data='item')
        div(class='galleryLeftController galleryController')
          img(src='~@/assets/image/svg/back.svg')
        div(class='galleryRightController galleryController')
          img(src='~@/assets/image/svg/next.svg')
  div.additionalLink
    div
      span 整合所有遊戲:
      span 暴雪 Battle.net 桌面應用程式
    div
      span 隨時隨地保持聯繫:
      span 暴雪 Battle.net 行動應用程式
</template>

<script>
import PaneTitle from '@/components/PaneTitle'
import GameGalleryItem from '@/components/GameGalleryItem'

const gameGalleryItemData = [
  {
    bg: require('../assets/image/gameList/game1.jpg'),
    instantBuy: false,
    freePlay: false
  },
  {
    bg: require('../assets/image/gameList/game2.jpg'),
    instantBuy: true,
    freePlay: false
  },
  {
    bg: require('../assets/image/gameList/game3.jpg'),
    instantBuy: true,
    freePlay: true
  },
  {
    bg: require('../assets/image/gameList/game4.jpg'),
    instantBuy: false,
    freePlay: true
  },
  {
    bg: require('../assets/image/gameList/game5.jpg'),
    instantBuy: false,
    freePlay: true
  },
  {
    bg: require('../assets/image/gameList/game6.jpg'),
    instantBuy: false,
    freePlay: false
  },
  {
    bg: require('../assets/image/gameList/game7.jpg'),
    instantBuy: false,
    freePlay: false
  },
  {
    bg: require('../assets/image/gameList/game8.jpg'),
    instantBuy: false,
    freePlay: false
  },
  {
    bg: require('../assets/image/gameList/game9.jpg'),
    instantBuy: false,
    freePlay: true
  },
  {
    bg: require('../assets/image/gameList/game10.jpg'),
    instantBuy: true,
    freePlay: false
  },
  {
    bg: require('../assets/image/gameList/game11.jpg'),
    instantBuy: true,
    freePlay: false
  }
]

export default {
  name: 'GameList',
  components: {
    PaneTitle,
    GameGalleryItem
  },
  data () {
    return {
      gameGalleryItemData: gameGalleryItemData,
      galleryLeftLimit: 0,
      galleryRightLimit: 0,
      galleryPos: 0
    }
  },
  mounted () {
    // detect gallery inner width to calculate the left/right limit
    let gallery = document.querySelector('div.gameListGalleryInner')
    let mask = document.querySelector('div.gameListGalleryContainer')
    this.galleryLeftLimit = (gallery.offsetWidth - mask.offsetWidth) * (-1)
    // auto change limit when screen width change
    window.addEventListener('resize', (e) => {
      this.galleryLeftLimit = (gallery.offsetWidth - mask.offsetWidth) * (-1)
      this.galleryPos = (this.galleryPos > this.galleryLeftLimit) ? this.galleryPos : this.galleryLeftLimit
      gallery.style.left = this.galleryPos + 'px'
    })
    // bind click event listener to the gallery left/right controller button
    document.querySelector('div.galleryRightController').addEventListener('click', (e) => {
      this.galleryPos = (this.galleryPos - 200 > this.galleryLeftLimit) ? this.galleryPos - 200 : this.galleryLeftLimit
      gallery.style.left = this.galleryPos + 'px'
    })
    document.querySelector('div.galleryLeftController').addEventListener('click', (e) => {
      this.galleryPos = (this.galleryPos + 200 < this.galleryRightLimit) ? this.galleryPos + 200 : this.galleryRightLimit
      gallery.style.left = this.galleryPos + 'px'
    })
  }
}
</script>

<style scoped>
#gameListContent {
  padding-top: 10vh;
  background-image: url('~@/assets/image/background/gameList.jpg');
  background-size: cover;
}

.gameListContainer {
  padding: 0 15vw;
  margin-bottom: 30px;
}

.gameListRow {
  margin-top: 20px;
}

.gameCellTitle {
  color: #fff;
  opacity: .3;
  font-size: 18px;
}

.gameListGalleryContainer {
  position: relative;
  overflow: hidden;
  height: 240px;
}

.gameListGalleryInner {
  position: relative;
  left: 0px;
  display: inline-flex;
  flex-flow: row nowrap;
  justify-content: flex-start;
  align-items: center;
  transition: left 0.3s ease;
}

.galleryController {
  width: 30px;
  height: 70px;
  background-color: #0e86ca;
  border: 1px solid #00aeff;
  position: absolute;
}

.galleryController:hover {
  cursor: pointer;
  background-color: #00aeff;
}

.galleryController > img {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.galleryLeftController {
  top: 85px;
  left: 20px;
}

.galleryRightController {
  top: 85px;
  right: 20px;
}

.additionalLink {
  font-size: 18px;
  padding: 15px 0;
  text-align: center;
  border-top: 1px solid rgba(255,255,255,0.3);
  border-bottom: 1px solid rgba(255,255,255,0.3);
}

.additionalLink > div {
  display: inline-block;
}

.additionalLink > div:first-child {
  border-right: 1px solid rgba(255,255,255,0.5);
  padding-right: 20px;
  margin-right: 20px;
}

.additionalLink > div > span {
  margin-right: 5px;
}

.additionalLink > div > span:nth-child(2) {
  color: #00aeff;
  transition: color 0.3s ease;
}

.additionalLink > div > span:nth-child(2):hover {
  cursor: pointer;
  color: #fff;
}
</style>
