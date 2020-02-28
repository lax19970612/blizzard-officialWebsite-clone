<template lang='pug'>
div.gameGalleryItem
  div.gameGalleryItemContainer
    div.gameGalleryItemBackground(:style="{ backgroundImage: 'url(' + data.bg + ')' } ")
    div.gameGalleryItemHoverContainer
      div.caption
        HomeSmallButton(buttonData='探索')
        div(v-if='data.instantBuy') 立即購買
        div(v-if='data.freePlay') 免費試玩
</template>

<script>
import HomeSmallButton from '@/components/HomeSmallButton'

export default {
  name: 'GameGalleryItem',
  components: {
    HomeSmallButton
  },
  props: {
    data: Object
  }
}
</script>

<style scoped>
.gameGalleryItem {
  padding: 20px 0;
  margin-left: 20px;
}

.gameGalleryItem:first-child {
  margin-left: 0;
}

.gameGalleryItemContainer {
  width: 167px;
  height: 200px;
}

.gameGalleryItemBackground {
  background-size: cover;
  background-position: center;
  width: 167px;
  height: 200px;
}

.gameGalleryItemHoverContainer {
  border: 1px solid transparent;
  width: 167px;
  height: 200px;
  position: relative;
  top: -200px;
  left: 0;
  padding: 20px 15px;
  background-color: rgba(0, 0, 0, 0);
  transition: background-color 0.3s ease;
}

.caption {
  position: relative;
  top: 20px;
  opacity: 0;
  transition: opaticy 0.3s ease, top 0.3s ease;
}

.gameGalleryItemContainer:hover .gameGalleryItemHoverContainer {
  background-color: rgba(0, 0, 0, 0.5);
  border-color: #00aeff;
}

.gameGalleryItemContainer:hover .caption {
  opacity: 1;
  top: 0;
}

.caption > div {
  color: #fff;
  width: 100%;
  text-align: center;
  padding: 10px 0;
  margin: 5px 0;
}

.caption > div:nth-child(3) {
  border-top: 1px solid rgba(255, 255, 255, 0.3);
}
</style>
