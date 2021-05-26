<template>
  <div class="container">
    <div class="header"></div>
    <div class="wrap">
      <div class="wrap-left"></div>
      <div class="wrap-right">
        <!-- 活动 -->
        <div class="top-box">
          <div class="activity">
            <img src="" alt="" class="act-img" />
            <div class="corner" :style="{ background: themeBgColor }">
              活动推荐
            </div>
          </div>
          <div class="rank">
            <div class="btnFont btn1" :style="{ color: themeColor }">
              排行榜 <svg-icon icon-class="arrow"></svg-icon>
            </div>
          </div>
          <div class="famous">
            <div class="btnFont btn2" :style="{ color: themeColor }">
              名家示范 <svg-icon icon-class="arrow"></svg-icon>
            </div>
          </div>
        </div>
        <!-- 分类 -->
        <div class="classify">
          <div class="item" v-for="(item, index) in 5" :key="index">
            <img src="" alt="" class="item-img" />
            <div class="item-info">
              <p class="info">xuangxiang</p>
              <p class="info">选项</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="guide"></div>
  </div>
</template>
<script>
export default {
  name: "Preview",
  data() {
    return {
      themeColor: "#2c8fff",
      themeBgColor: "linear-gradient(312deg, #5a82ff 0%, #3badff 100%)",
      bgImg: ["", ""],
      classifyList: [],
    };
  },
};
</script>
<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
  border: 0 none;
}
@mixin flex($content: space-between, $items: null) {
  display: flex;
  justify-content: $content;
  @if $items {
    align-items: $items;
  }
}
.common {
  @include flex(center, center);
  position: absolute;
  top: 151px;
  height: 36px;
}
.container {
  position: relative;
  box-sizing: border-box;
  margin: 0 auto;
  width: 1280px;
  height: 720px;
  // background: linear-gradient(315deg, #305de9 0%, #3b95ff 100%);
  background: url("https://reading.oss.iyougu.com/tc/uploads/images/b070e2cd7abf4b89ac38cd91871b1ed9.png")
    no-repeat;
  background-size: 100% 100%;
  .header {
    width: 100%;
    height: 73px;
    background: rgba(255, 255, 255, 0.2);
  }
  .wrap {
    box-sizing: border-box;
    @include flex();
    width: 100%;
    margin-top: 34px;
    padding-left: 42px;
    padding-right: 52px;
    .wrap-left {
      margin-right: 26px;
      width: 301px;
      height: 563px;
      background: url("https://reading.oss.iyougu.com/uploads/terminalPreview/bg_1.png")
        no-repeat;
      background-size: 100% 100%;
    }
    .wrap-right {
      flex: 1;
      .top-box {
        @include flex();
        margin-bottom: 27px;
        .activity {
          position: relative;
          width: 425px;
          height: 203px;
          border-radius: 5px;
          box-shadow: 0 7px 13px 0 rgba(0, 0, 0, 0.1);
          overflow: hidden;
          background: #fff;
          .act-img {
            width: 100%;
            height: 100%;
          }
          .corner {
            @extend .common;
            right: 0;
            width: 81px;
            border-radius: 67px 0 0 67px;
            color: #fff;
            font-size: 16px;
            box-shadow: 0 7px 13px 0 rgba(0, 0, 0, 0.1);
            z-index: 1;
          }
        }
        .rank {
          position: relative;
          width: 203px;
          height: 203px;
          border-radius: 5px;
          background: url("https://reading.oss.iyougu.com/uploads/terminalPreview/bg_list.png")
            no-repeat;
          background-size: 100% 100%;
        }
        .famous {
          @extend .rank;
          background: #ccc;
        }
        .btnFont {
          @extend .common;
          border-radius: 18px;
          background: #fff;
          font-size: 20px;
          left: 50%;
          transform: translateX(-50%);
          z-index: 1;
          &.btn1 {
            width: 116px;
          }
          &.btn2 {
            width: 138px;
          }
        }
      }
      .classify {
        @include flex(flex-start);
        flex-flow: wrap;
        .item {
          position: relative;
          width: 277px;
          height: 160px;
          margin-bottom: 13px;
          margin-right: 13px;
          background: #ccc;
          border-radius: 5px;
          overflow: hidden;
          &:nth-child(3n) {
            margin-right: 0;
          }
          .item-img {
            width: 100%;
            height: 100%;
          }
          .item-info {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 48px;
            background: rgba(255, 253, 242, 0.5);
            box-shadow: 0 7px 13px 0 rgba(0, 0, 0, 0.1);
            text-align: center;
            .info {
              line-height: 1.1;
              color: #444;
              font-size: 20px;
              letter-spacing: 10px;
              &:first-child {
                margin-top: 8px;
                margin-bottom: 2px;
                font-size: 9px;
                letter-spacing: 1px;
              }
            }
          }
        }
      }
    }
  }
  .guide {
    position: absolute;
    right: 20px;
    top: 118px;
    width: 17px;
    height: 91px;
    background: url("https://reading.oss.iyougu.com/uploads/terminalPreview/bg_zhiyin.png")
      no-repeat;
    background-size: 100% 100%;
    z-index: 1;
  }
}
</style>
