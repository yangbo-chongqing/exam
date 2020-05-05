<template>
  <div class="home-cont">
    <img class="img-banner" src="@/assets/images/banner.png" alt="banner.png">
    <div class="sub-nav-wrap">
      <div 
      :class="['sub-nav', {'waiting': !item.open}, {'active': index === active}]" 
      v-for="(item, index) in navList" 
      :key="index"
      @click="jump(item, index)">
        <img class="img-sound" src="@/assets/images/sound.png" alt="sound.png">
        <b class="point"></b>
        {{item.txt}}
        <img class="img-jump" src="@/assets/images/arrow_b.png" alt="go.png">
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      active: 3,
      navList: [
        {path: '/', txt: '开幕致辞', open: true},
        {path: '/', txt: '主题演讲', open: true},
        {path: '/', txt: 'Paddle 2.0 Alpha发布', open: true},
        {path: '/', txt: 'Easydata 全新发布', open: true},
        {path: '/', txt: '教育传承：青苗计划发布', open: false},
        {path: '/', txt: '开源共建：KOL激励计划发布', open: false},
      ]
    }
  },
  methods: {
    jump (item, index) {
      if (!item.open) return;
      this.active = index
    }
  }
}
</script>
<style lang="scss">
@import '@/assets/scss/var.scss';

.home-cont {
  display: flex;background-color: #005eef;padding: 1px;
  border-radius: 5px;overflow: hidden;
  .sub-nav-wrap {
    flex: 1;display: flex;flex-direction: column;justify-content: space-between;
    border-top-right-radius: 5px;border-bottom-right-radius: 5px;overflow: hidden;
    margin-bottom: -1px;
    .sub-nav {
      display: flex;flex: 1;align-items:center;color: rgba(#fff, .7);
      background-color: #062db4;padding: 0 40px;position: relative;border-bottom: 1px solid #005eef;
      position: relative;cursor: pointer;
      .point {
        width: 4px;height: 4px;border-radius: 2px;background-color: $color;
        margin-right: 10px;
      }
      .img-jump {
        position: absolute;right: 20px;top: 50%;
        height: 16px;margin-top: -8px;
      }
      .img-sound {
        position: absolute;left: 10px;top: 50%;
        height: 14px;margin-top: -7px;
        width: auto;display: none;
      }
      &.active {
        .img-sound {
          display: block;
        }
      }
      &.waiting {
        color: rgba(#fff, .3);cursor: not-allowed;
        .point {
          background-color: rgba(#fff, .3);
        }
        .img-jump {
          opacity: .7;
        }
      }
    }
  }
}
</style>