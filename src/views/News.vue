<template lang="pug">
div#news
  div.newsContainer
    PaneTitle(HeadingText="重要消息" HeadingSubtext="所有消息")
    div.cardsContainer
      NewsCard(v-for="(item, index) in cardsData" :key='index' :data='item')
</template>

<script>
import PaneTitle from '@/components/PaneTitle'
import NewsCard from '@/components/NewsCard'

const cardsData = [
  {
    cardImage: require('@/assets/image/news/new1.jpg'),
    contentTitle: '《爐石戰記》',
    storiesTitle: '龍類降臨英雄戰場 – 更新檔 16.4 說明 – 2 月 27 日'
  },
  {
    cardImage: require('@/assets/image/news/new2.jpg'),
    contentTitle: '深入暴雪',
    storiesTitle: '火爆的戰爭場面在《決勝時刻®：現代戰爭®》第二季中繼續上演'
  },
  {
    cardImage: require('@/assets/image/news/new3.jpg'),
    contentTitle: 'war3',
    storiesTitle: '《魔獸爭霸 III》淬鍊重生正式推出！'
  }
]

export default {
  name: 'News',
  components: {
    PaneTitle,
    NewsCard
  },
  data () {
    return {
      cardsData: cardsData
    }
  },
  mounted () {
    let card = document.querySelector('div.newsCard')
    // card image height init
    document.querySelectorAll('div.cardImgWrapper').forEach((item) => {
      item.style.height = ((card.offsetWidth * 0.5 > 106) ? card.offsetWidth * 0.5 : 106) + 'px'
    })
    // add resize listener to auto change the height of card
    window.addEventListener('resize', (e) => {
      document.querySelectorAll('div.cardImgWrapper').forEach((item) => {
        item.style.height = ((card.offsetWidth * 0.5 > 106) ? card.offsetWidth * 0.5 : 106) + 'px'
      })
    })
  }
}
</script>

<style scoped>
#news {
  padding: 10vh 0;
  background-image: url('~@/assets/image/background/news.jpg');
  background-size: cover;
}

.newsContainer {
  padding: 0 15vw;
}

.cardsContainer {
  margin-top: 30px;
  display: flex;
  justify-content: space-between;
}

.newsCard {
  width: 22vw;
  min-width: 212px;
  background-color: rgba(0, 174, 255, 0.1);
  overflow: hidden;
  cursor: pointer;
  border: 1px solid rgba(255,255,255,0.3);
  transition: border-color 0.3s ease, background-color 0.3s ease;
}

.newsCard:last-child {
  margin: 0;
}

.cardImage {
  background-image: url('~@/assets/image/news/new1.jpg');
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
  color: rgba(255,255,255,0.5);
  font-size: 12.8px;
}

.cardStoriesTitle {
  font-size: 16px;
  font-weight: 700;
  line-height: 1.4;
}

.newsCard:hover {
  background-color: rgba(0,174,255,0.15);
  border-color: #00aeff;
}

.newsCard:hover .cardImage {
  transform: scale(1.1);
}
</style>
