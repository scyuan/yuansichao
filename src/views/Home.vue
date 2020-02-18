<template>
  <div class="home">
    <p class="page trans10">
      <span v-for="(w,index) of name" :key="index">{{ w }}</span>
    </p>
    <div class="mario-wrap trans10">
      <div
        class="mario"
        v-for="(src,index) of marios"
        :key="index"
        :style="{'background-image':`url(${src})`}"
      ></div>
    </div>
    <div class="menu trans10">
      <a>施</a>
      <a>工</a>
      <a>中</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "home",
  data() {
    return {
      name: `Jackie's page`.split(""),
      marios: [
        require("../assets/mario.jpeg"),
        require("../assets/xiaolv.jpeg"),
        require("../assets/xiaohong.jpeg")
      ]
    };
  }
};
</script>
<style lang="scss" scoped>
@import url("https://fonts.font.im/css?family=Audiowide");
.home {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.mario-wrap {
  width: 400px;
  height: 100px;
  display: flex;
  justify-content: space-around;

  .mario {
    width: 100px;
    height: 100px;
    background-size: 100% 100%;
  }
}

.page {
  font-family: "Audiowide", cursive;
  width: 360px;
  display: flex;
  justify-content: space-around;
  font-size: 30px;
  position: relative;
  color: #fff;
  animation: fadeIn 0.8s ease-in forwards;
  animation-delay: 1s;
  &::after {
    content: "";
    display: block;
    position: absolute;
    height: 100%;
    width: 100%;
    z-index: 2;
    background: #222;
    left: 0;
    top: 0;
    transform: scaleX(0);
    transform-origin: left;
    animation: slide 2s cubic-bezier(0.75, 0, 0, 1) forwards;
  }
}
@keyframes fadeTop {
  to {
    transform: translate(0, 0);
    opacity: 1;
  }
}
@keyframes slide {
  50% {
    transform: scaleX(1);
    transform-origin: left;
  }
  50.1% {
    transform-origin: right;
  }
  to {
    transform: scaleX(0);
    transform-origin: right;
  }
}
@keyframes fadeIn {
  to {
    color: #000;
  }
}
@font-face {
  font-family: "webfont";
  font-display: swap;
  src: url("//at.alicdn.com/t/webfont_fie52771qxt.eot"); /* IE9*/
  src: url("//at.alicdn.com/t/webfont_fie52771qxt.eot?#iefix")
      format("embedded-opentype"),
    /* IE6-IE8 */ url("//at.alicdn.com/t/webfont_fie52771qxt.woff2")
      format("woff2"),
    url("//at.alicdn.com/t/webfont_fie52771qxt.woff") format("woff"),
    /* chrome、firefox */ url("//at.alicdn.com/t/webfont_fie52771qxt.ttf")
      format("truetype"),
    /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/
      url("//at.alicdn.com/t/webfont_fie52771qxt.svg#Alibaba-PuHuiTi-Regular")
      format("svg"); /* iOS 4.1- */
}
.menu {
  font-family: "webfont";
  width: 400px;
  display: flex;
  justify-content: space-around;
  a {
    cursor: pointer;
    display: inline-block;
    position: relative;
    color: #000;
    text-decoration: none;
    &::after {
      content: "";
      height: 2px;
      display: block;
      position: absolute;
      background: #000;
      width: 100%;
      left: 0;
      bottom: -4px;
      transform: scaleX(0);
      transform-origin: right;
      transition: transform 0.5s;
    }
    &:hover::after {
      transform: scaleX(1);
      transform-origin: left;
    }
  }
}
.trans10 {
  transform: translate(0, -10vh);
}
</style>
