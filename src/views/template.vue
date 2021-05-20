<template>
  <div class="container">
    <div class="box">
      <img :src="bgImg[0]" alt="背景图" class="box-bg" />
      <img src="./assets/img_download.png" alt="登录" class="box-img1" />
      <p class="descript">登陆页</p>
    </div>
    <div class="box">
      <img :src="bgImg[1]" alt="背景图" class="box-bg" />
      <img src="./assets/img_home.png" alt="首页" class="box-img2" />
      <p class="descript">首页</p>
      <div class="corner" :style="{ background: themeBgColor }">活动推荐</div>
      <div class="btn btn1" :style="{ color: themeColor }">
        排行榜 <svg-icon icon-class="arrow"></svg-icon>
      </div>
      <div class="btn btn2" :style="{ color: themeColor }">
        名家示范 <svg-icon icon-class="arrow"></svg-icon>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Template",
  data() {
    return {
      themeColor: "#2c8fff",
      themeBgColor: "linear-gradient(312deg, #5a82ff 0%, #3badff 100%)",
      bgImg: ["", ""],
    };
  },
};
</script>
<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
}
%flex {
  display: flex;
  align-items: center;
}
.index1 {
  position: relative;
  z-index: 1;
}
.common {
  @extend %flex;
  justify-content: center;
  position: absolute;
  top: 36.2%;
  height: 5%;
}
.container {
  box-sizing: border-box;
  margin: 0 auto;
  padding: 30px 20px;
  width: 1280px;
  min-height: 408px;
  display: flex;
  justify-content: space-around;
  .box {
    width: 600px;
    height: 338px;
    position: relative;
    text-align: center;
    .box-bg {
      width: 100%;
      height: 338px;
      position: absolute;
      left: 0;
      top: 0;
      background: #2c8fff;
      z-index: 0;
    }
    .box-img1 {
      @extend .index1;
      width: 100%;
      height: 302px;
      margin-top: 36px;
    }
    .box-img2 {
      @extend .index1;
      width: 100%;
      height: 325px;
      margin-bottom: 13px;
    }
    .descript {
      margin-top: 10px;
      line-height: 1.4;
      color: #333;
      font-size: 14px;
    }
    .corner {
      @extend .common;
      right: 38%;
      width: 7.08%;
      border-radius: 31.25px 0 0 31.25px;
      color: #fff;
      font-size: 7.5px;
      box-shadow: 0 3.12px 6.25px 0 rgba(0, 0, 0, 0.1);
      z-index: 1;
    }
    .btn {
      @extend .common;
      border-radius: 8.53px;
      background: #fff;
      font-size: 9.37px;
      z-index: 1;
      &.btn1 {
        width: 9.06%;
        right: 24.4%;
      }
      &.btn2 {
        width: 10.7%;
        right: 6.7%;
      }
    }
  }
}
</style>
