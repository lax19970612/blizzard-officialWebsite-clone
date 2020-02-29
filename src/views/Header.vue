<template lang="pug">
nav#Header
  div.headerLogo
  div.headerNavbarItems
    a 遊戲
    a 商店
    a 最新消息
    a 電子競技
    a BLIZZCON
  div.headerNavbarProfileItems
    a 客服支援
    a 我的帳號
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
#Header {
  width: 100%;
  height: 60px;
  background-color: rgba(255,255,255,0.05);
  position: absolute;
  z-index: 999;
  padding: 0 15vw;
  display: flex;
}

.headerLogo {
  cursor: pointer;
  background-image: url('~@/assets/image/svg/blizzardUpperLogo.svg');
  background-repeat: no-repeat;
  background-size: 75.06px 34px;
  background-position: center;
  height: 100%;
  width: 75.06px;
  margin-right: 30px;
}

.headerNavbarItems, .headerNavbarProfileItems {
  display: flex;
  align-items: center;
}

.headerNavbarItems > a {
  color: rgba(255,255,255,0.7);
  transform: color 0.2s;
  cursor: pointer;
  margin-right: 30px;
  font-size: 20px;
}

.headerNavbarItems > a:hover, .headerNavbarProfileItems > a:hover{
  color: #fff;
}

.headerNavbarProfileItems {
  position: absolute;
  right: 15vw;
  height: 100%;
}

.headerNavbarProfileItems > a {
  color: rgba(255,255,255,0.7);
  transform: color 0.2s;
  cursor: pointer;
  font-size: 17px;
  margin-left: 30px;
}
</style>
