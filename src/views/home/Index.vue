<template>
  <div class="home">
    <div class="home-content">
      <div class="home-banner">
        <div class="title cl-primary">会议大厅 Conference Hall</div>
        <div class="home-pre">9999人正在观看直播
          <img class="img-share" src="@/assets/images/share.png" alt="share.png">
        </div>
      </div>
      <Cont />
      <Foot />
    </div>
  </div>
</template>

<script>
import Cont from './Cont'
import Foot from './Foot'
export default {
  name: 'Home',
  data () {
    return {
    }
  },
  components: {
    Cont, Foot
  }
}
</script>

<style lang="scss">
  @import '@/assets/scss/var.scss';

  .home {
    $margin: 10px;
    height: 100%;
    background: url('~@/assets/images/bg.png') no-repeat;
    background-size: 100% auto;
    .active {
     background-image: linear-gradient(to right, $color_p, $color_b); 
    }
    &-content {
      padding: $padding;width: $screen_width;margin: 0 auto;background-color: rgba(2, 23, 71, .9);
      border-bottom-left-radius: 5px;border-bottom-right-radius: 5px;
    }
    &-banner {
      display: flex;justify-content: space-between;margin-bottom: $margin;
      .title {
        font-size: 14px;
      }
      .img-share {
        height: 14px;display: inline-block;vertical-align: top;
        margin: 5px 0 0 5px;cursor: pointer;
      }
    }
    &-cont {
      margin-bottom: $margin;
    }
    .img-bg {
      width: 100%;
    }
  }
</style>