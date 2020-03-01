<template lang='pug'>
div.newsCard
  div.cardImgWrapper
    div(class='cardImage' :style="{ backgroundImage: 'url(' + data.cardImage + ')' }")
  div.cardContent
    div.cardContentTitle {{ data.contentTitle }}
    div.cardStoriesTitle {{ data.storiesTitle }}
</template>

<script>
export default {
  name: 'NewsCard',
  props: {
    data: Object
  }
}
</script>

<style>
.newsCard {
  width: 22vw;
  min-width: 212px;
  background-color: rgba(0, 174, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.3);
  overflow: hidden;
  cursor: pointer;
  transition: border-color 0.3s ease, background-color 0.3s ease;
}

.cardImage {
  background-size: 100% auto;
  background-position: center;
  height: 100%;
  transition: transform 0.3s ease;
}

.cardContent {
  min-height: 200px;
  padding: 30px;
}

.cardContentTitle {
  color: rgba(255, 255, 255, 0.5);
  font-size: 12.8px;
}

.cardStoriesTitle {
  color: #fff;
  font-size: 16px;
  font-weight: 700;
  line-height: 1.4;
}

.newsCard:hover {
  background-color: rgba(0, 174, 255, 0.15);
  border-color: #00aeff;
}

.newsCard:hover .cardImage {
  transform: scale(1.1);
}
</style>
