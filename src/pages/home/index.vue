<template>
  <div class="page">
    <div class="page__bd">
      <div class="weui-tab">
        <div class="weui-navbar">
          <block v-for="(item,index) in tabs" :key="index">
            <div :id="index" :class="{'weui-bar__item_on':activeIndex == index}" class="weui-navbar__item" @click="tabClick">
              <div class="weui-navbar__title">{{item}}</div>
            </div>
          </block>
          <div class="weui-navbar__slider" :class="navbarSliderClass"></div>
        </div>
        <div class="weui-tab__panel">
          <div class="weui-tab__content" :hidden="activeIndex != 0"><swiperView/><weatherView/></div>
          <div class="weui-tab__content" :hidden="activeIndex != 1"><readView/></div>
          <div class="weui-tab__content" :hidden="activeIndex != 2"><musicView/></div>
          <div class="weui-tab__content" :hidden="activeIndex != 3"><vedioView/></div>
          <div class="weui-tab__content" :hidden="activeIndex != 4">
                <button type="success">success </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import swiperView from './swiper'
import weatherView from './weather'
import readView from '../reader'
import musicView from './music'
import vedioView from './vedio'
// window.fly = fly
export default {
  data () {
    return {
      tabs: ['首页', '阅读', '音乐', '影视', '新闻'],
      activeIndex: '0',
      fontSize: 30
    }
  },
  components: {
    swiperView,
    weatherView,
    readView,
    musicView,
    vedioView
  },
  computed: {
    navbarSliderClass () {
      if (this.activeIndex === '0') {
        return 'weui-navbar__slider_0'
      }
      if (this.activeIndex === '1') {
        return 'weui-navbar__slider_1'
      }
      if (this.activeIndex === '2') {
        return 'weui-navbar__slider_2'
      }
      if (this.activeIndex === '3') {
        return 'weui-navbar__slider_3'
      }
      if (this.activeIndex === '4') {
        return 'weui-navbar__slider_4'
      }
    }
  },
  methods: {
    tabClick (e) {
      console.log(e)
      this.activeIndex = e.currentTarget.id
    }
  }
}
</script>

<style scoped>
page,
.page,
.page__bd {
  height: 100%;
}
.page__bd {
  padding-bottom: 0;
}
.weui-tab__content {
  padding-top: 0;
  text-align: center;
}
.weui-navbar__slider_0 {
  left: 19rpx;
  transform: translateX(0);
}
.weui-navbar__slider_1 {
  left: 19rpx;
  transform: translateX(150rpx);
}
.weui-navbar__slider_2 {
  left:19rpx;
  transform: translateX(300rpx);
}
.weui-navbar__slider_3 {
  left:19rpx;
  transform: translateX(450rpx);
}
.weui-navbar__slider_4 {
  left:19rpx;
  transform: translateX(600rpx);
}
.weui-navbar__slider{
  width: 3em;
}
</style>