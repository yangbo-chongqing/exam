<template>
  <div class="header">
    <div class="screen-wrap">
      <div class="logo title">
        <div class="txt-wave">WAVE</div>
        <div class="txt-summit">SUMMIT</div>
      </div>
      <div class="top-nav">
        <router-link
          class="nav-item"
          tag="div"
          v-for="(item, index) in list"
          :to="item.path"
          :key="index"
        >{{item.txt}}</router-link>
      </div>
      <div class="right-msg">
        <router-link class="right-item" to="/speech">积分兑换</router-link>
        <router-link class="right-item" to="/speech">帮助</router-link>
        <div class="right-item sigin-btn">登入</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      list: [
        { path: "/", txt: "会议大厅" },
        { path: "/s", txt: "演讲大厅" },
        { path: "/v", txt: "公开课" },
        { path: "/q", txt: "展示大厅" },
        { path: "/r", txt: "互动大厅" }
      ]
    };
  }
};
</script>
<style lang="scss">
@import "@/assets/scss/var.scss";
.header {
  height: $hight;
  .screen-wrap {
    display: flex;
    box-sizing: border-box;
    line-height: $hight;
    height: 100%;
    width: $screen_width;
    margin: 0 auto;
    .logo {
      display: inline-block;
      font-size: 16px;
      padding: 0 $padding;
      font-weight: 800;
      .txt-wave,
      .txt-summit {
        background: linear-gradient(to right, $color_p, $color_g);
        background-clip: text;
        color: transparent;
        height: $hight * 0.5;
        line-height: $hight * 0.3;
      }
      .txt-wave {
        line-height: $hight * 0.7;
      }
    }
    .top-nav {
      padding: 0 $padding;
      margin: 0 $padding;
      font-size: 14px;
      display: flex;
      justify-content: space-between;
      .nav-item {
        margin: 0 $padding * 0.5;
        padding: 0 $padding * 0.5;
        cursor: pointer;
        position: relative;
      }
      .router-link-exact-active {
        &::after {
          content: "";
          position: absolute;
          left: 0;
          right: 0;
          bottom: 0;
          height: 2px;
          background-image: linear-gradient(to right, $color_p, $color_g);
        }
      }
    }
    .right-msg {
      flex: 1;
      display: flex;
      justify-content: flex-end;
      padding: 0 $padding;
      align-items: center;
      .right-item {
        margin: 0 $padding * 0.4;
      }
      .sigin-btn {
        display: inline-block;
        cursor: pointer;
        height: 18px;
        line-height: 18px;
        padding: 0 4px;
        border: 1px solid $color;
        border-radius: 2px;
      }
    }
  }
}
</style>