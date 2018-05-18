<template>
  <view class="page">
  <view class="page__hd">
    <text class="page__title">电影徘行</text>
    <!-- <text class="page__desc">图片</text> -->
  </view>
  <view class="page__bd">
    <view class="section section_gap image-card" v-for="(item, index) in moviesList" :key="index">
      <view class="section__ctn">
        <img class="ctn-image" style="background-color: #eeeeee;" mode="scaleToFill" :src="item.img"/>
        <view class="movieSc">{{item.sc}}</view> 
      </view>     
      <view class="section__title">{{item.nm}}</view>
    </view>
  </view>
</view>
</template>

<script>
import Fly from 'flyio/dist/npm/wx'
let fly = new Fly()
export default {
  data () {
    return {
      array: [{
        mode: 'scaleToFill',
        text: '使图片完全适应'
      }, {
        mode: 'scaleToFill',
        text: 'aspectFit'
      }],
      src: 'http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg',
      moviesList: null
    }
  },
  methods: {
    imageError: function (e) {
      console.log('image3发生error事件，携带值为', e.detail.errMsg)
    }
  },
  mounted () {
    fly.get('http://m.maoyan.com/movie/list.json?type=hot&offset=0&limit=10').then(
        res => {
          this.moviesList = res.data.data.movies
          console.log('接口', this.moviesList)
        }
      )
      .catch(
        err => {
          console.log(err)
        }
      )
  }
}
</script>

<style>
.image-card{
  width:46vw;
  float:left;
  padding:10rpx;
}
.ctn-image{
  width: 44vw;
  /* height: 100px; */
}
.section__title{
  font-size: 16px;
}
.section__ctn{
  position: relative;
}
.movieSc{
  position: absolute;
  right: 5px;
  bottom: 5px;
  color: goldenrod;
  font-size: 18px;
}
</style>
