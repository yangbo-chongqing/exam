<template>
  <div class="home-foot">
    <div class="foot-left">
      <div class="foot-title">
        <div class="sub-tit">
          <span class="cl-primary">
            <img src="@/assets/images/arrow_b.png" class="img-icon" alt="">
            获奖信息：
          </span>
          用户xxxxxxxxx
        </div>
        <div class="sub-tit">
          <span class="cl-primary">
            <img src="@/assets/images/arrow_b.png" class="img-icon" alt="">
            社区互动：
          </span>
          展示大厅xxxxxxxx
        </div>
      </div>
      <div class="foot-box">
        <div :class="['item', {'active': index === active}]" v-for="(item, index) in list" :key="index">
          <img class="img-item" :src="item.img" alt="item.png">
          <div>{{item.txt}}</div>
        </div>
      </div>
    </div>
    <div class="foot-right">
      <div class="sub-tit cl-primary">公开课 Open Class</div>
      <div class="btn-big btn">飞将2.0公开课</div>
      <div class="btn-small btn active">AL大咖分享大卡经验</div>
      <div class="btn-small btn">AL大咖分享大卡经验</div>
      <div class="btn-small btn">AL大咖分享大卡经验</div>
      <div class="btn-small btn">AL大咖分享大卡经验</div>
    </div>
  </div>
</template>
<script>
import cpu from '@/assets/images/cpu.png'
import phone from '@/assets/images/phone_s.png'
import redeem from '@/assets/images/redeem.png'
import transfer from '@/assets/images/transfer.png'
export default {
  data () {
    return {
      active: 0,
      list: [{img: cpu, txt: '展示大厅'}, 
      {img: transfer, txt: '互动大厅'}, 
      {img: redeem, txt: '积分换礼'}, 
      {img: phone, txt: '官方社群'}]
    }
  }
}
</script>
<style lang="scss">
  @import '@/assets/scss/var.scss';

  .home-foot {
    display: flex;justify-content: space-between;
    .foot-title {
      margin-bottom: 10px;
      .img-icon {
        display: inline-block;vertical-align: top;margin-top: 4px;
      }
    }
    .foot-box {
      display: flex;
      .img-item {
        width: 30px;
      }
      .item {
        border: 1px solid $color_b;border-radius: 5px;margin-right: 20px;
        padding: 15px 25px;text-align: center;color: #3a71b1;
        &.active {
          color: #fff;
        }
      }
    }
    .foot-right {
      width: 403px;display: flex;flex-wrap: wrap;
      justify-content: space-between;align-items: center;
      .sub-tit {
        width: 100%;
      }
      .btn {
        width: 49%;background-color: #062db4;border: 1px solid $color_b;
        border-radius: 3px;margin-top: 5px;text-align: center;padding: 3px 0;
      }
      .btn-big {
        width: 100%;
      }
    }
  }
</style>