<template lang="pug">
div#Footer
  div.footerContent
    div.footerLogoContainer
      div(class='footerLogo footerUpperLogo')
      div(class='footerLogo footerLowerLogo')
    div(class='footerLinks footerMainLinks')
      div
        a 工作機會
      div
        a 關於
      div
        a 客服支援
      div
        a 聯繫我們
      div
        a 媒體報導
      div
        a API
    div.footerCopyright ©2020 美商暴雪娛樂股份有限公司（Blizzard Entertainment, Inc.）版權所有。
    div.footerTrademark
      span 在此提及的所有
      a 商標
      span 是其各自所有人的財產。
    div(class='footerLinks footerSublinks')
      div
        a 隱私
      div
        a 法律聲明
      div
        a 條款
      div
        a COOKIES
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped>
#Footer {
  padding-top: 80px;
  background-image: url('~@/assets/image/background/footer.jpg');
  background-position: top center;
  background-size: cover;
}

.footerContent {
  padding-top: 20px;
  padding-bottom: 60px;
}

.footerLogoContainer {
  width: 124px;
  height: 66px;
  margin: 30px auto;
  position: relative;
}

.footerLogo {
  cursor: pointer;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-size: 124px 66px;
}

.footerUpperLogo {
  background-image: url('~@/assets/image/svg/blizzardUpperLogo.svg');
}

.footerLowerLogo {
  background-image: url('~@/assets/image/svg/blizzardLowerLogo.svg');
}

.footerLinks {
  width: 100%;
  display: inline-flex;
  justify-content: center;
}

.footerMainLinks {
  margin: 15px 0;
  font-size: 17px;
}

.footerLinks > div:nth-child(n+2):before {
  content: '';
  display: inline-block;
  height: 10px;
  width: 1px;
  background-color: rgba(255,255,255,0.3);
  margin: 0 15px;
  pointer-events: none;
}

.footerCopyright, .footerTrademark {
  font-size: 13px;
  color: rgba(255,255,255,0.3);
  line-height: 1.4;
  text-align: center;
  text-transform: uppercase;
}

.footerTrademark a, .footerLinks a {
  color: rgba(255,255,255,0.7);
  text-decoration: none;
  transition: color 0.2s;
  cursor: pointer;
}

.footerTrademark a:hover, .footerLinks a:hover {
  color: rgba(255,255,255,1);
}

.footerSublinks {
  font-size: 13px;
}
</style>
