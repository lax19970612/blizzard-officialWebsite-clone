<template lang='pug'>
  div.carousel-caption
    img(class='animated bounceInRight fast' :src='imgSrc')
    h3(class='animated bounceInRight fast') {{ captionTitle }}
    HomeButton(v-bind:buttonData='ButtonText' class='button animated bounceInRight fast')
</template>

<script>
import HomeButton from './HomeButton'

export default {
  name: 'CarouselCaption',
  components: {
    HomeButton
  },
  props: {
    imgSrc: String,
    captionTitle: String,
    ButtonText: String
  },
  data () {
    return {
    }
  }
}
</script>

<style scoped>
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
  animation-delay: 1s;
}

</style>
