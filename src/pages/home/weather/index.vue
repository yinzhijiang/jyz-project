<template>
  <div class="center">
    <div class="weui-flex">
        <div class="weui-flex__item">
          <div class="placeholder">
            <text class="iconfont icon-weather"></text>
          </div>
          <span>天气</span>
        </div>
        <div class="weui-flex__item">
          <div class="placeholder">
            <i class="iconfont icon-map"></i>
            <span>位置</span>
          </div>
        </div>
        <div class="weui-flex__item">
          <div class="placeholder">
            <i class="iconfont icon-life"></i>
            <span>生活</span>
          </div>
        </div>
        <div class="weui-flex__item">
          <div class="placeholder">
            <i class="iconfont icon-like"></i>
            <span></span>
          </div>
        </div>
      </div>
    <!-- <span>当前位置</span><input type="text">
    <button type="disabled" @click="requestData">请求</button> -->
  </div>
</template>

<script>
// import Fly from 'flyio/dist/npm/wx'
export default {
  data () {
    return {
      // contentWeather: null
    }
  },
  methods: {
  //   requestData () {
  //     let fly = new Fly()
  //     fly.get('https://way.jd.com/he/freeweather', {
  //       city: 'beijing',
  //       appkey: 'a5621db2248ac0df73a7e91463775d89'
  //     }).then(res => {
  //       console.log(res.data.result.HeWeather5[0])
  //       wx.hideLoading()
  //     })
  //   }
  // },
  // mounted () {
  //   wx.getLocation({
  //     type: 'gcj02', // 返回可以用于wx.openLocation的经纬度
  //     success: function (res) {
  //       console.log(res)
  //       var latitude = res.latitude
  //       var longitude = res.longitude
  //       console.log(latitude, longitude)
  //       // wx.openLocation({
  //       //   latitude: latitude,
  //       //   longitude: longitude,
  //       //   scale: 28
  //       // })
  //     }
  //   })
  }
}
</script>

<style scoped>
.center{
  margin-top:2vh;
}
.placeholder{
  border-radius: 5px;
  margin: 5px;
  padding: 0 10px;
  text-align: center;
  /* background-color: rgba(0,0,0,0.1); */
  height: 2.3em;
  line-height: 2.3em;
  color: #cfcfcf;
}
.iconfont {
  font-family:"iconfont" !important;
  font-size:34px;
  font-style:normal;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #1aad19;
  text-shadow: 1px 1px gray;
} 
</style>
