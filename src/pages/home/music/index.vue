<template>
  <div class="music-list">
    <div class="weui-cells__title"><h2>热歌榜</h2></div>
    <div class="weui-cells weui-cells_after-title content-ft">
      <navigator  @click="musicPlay(index, item)" url="" class="weui-cell weui-cell_access" hover-class="weui-cell_active" v-for="(item,index) in songList" :key='index'>
        <div class="weui-cell__hd" style="width:2.5vw; position: relative;margin-right: 10px;">
          <i v-show="index !== i">{{index + 1}}</i>
          <i v-show="index == i" class="iconfont icon-voice"></i>
        </div>
        <div class="weui-cell__bd over-content" style="">
          <div>{{item.title}}</div>
          <div style="font-size: 13px;color: #888888;">{{item.author}} <span class="album-title">{{item.album_title}}</span></div>
        </div>
        <div class="weui-cell__ft weui-cell__ft_in-access"></div>
      </navigator>
    </div>
    <div class="fix-footer over-content">
      <navigator url="" class="weui-media-box weui-media-box_appmsg" hover-class="weui-cell_active">
        <!-- <div class="weui-media-box__hd weui-media-box__hd_in-appmsg">
          <image class="weui-media-box__thumb" :src="musicSrc" />
        </div> -->
        <!-- <div class="weui-media-box__bd weui-media-box__bd_in-appmsg">
          <div class="weui-media-box__title">{{musicName}}</div>
          <div class="weui-media-box__desc">由各种</div>
        </div> -->
        <audio :poster='musicSrc' :name='musicName' :author='musicAuthor'  :src="songSrc" id="myAudio" width="100vw" height="auto" controls loop></audio>
      </navigator>
    </div>
  </div>
</template>
 
<script>
import Fly from 'flyio/dist/npm/wx'
let fly = new Fly()
export default {
  data () {
    return {
      songList: null,
      i: -1,
      musicName: '',
      musicSrc: '',
      musicAuthor: '',
      songId: '',
      songSrc: '',
      audioCtx: null
    }
  },
  methods: {
    musicPlay (index, item) {
      this.i = index
      this.musicName = item.title
      this.musicAuthor = item.author
      this.musicSrc = item.pic_small
      this.songId = item.song_id
      fly.get('http://tingapi.ting.baidu.com/v1/restserver/ting?method=baidu.ting.song.play&songid=' + this.songId).then(
      res => {
        this.songSrc = res.engine.responseText.bitrate.file_link
        console.log(1111, this.songSrc)
      }
    )
      .catch(
        err => console.log(err)
      )
    }
  },
  mounted () {
    fly.get('http://tingapi.ting.baidu.com/v1/restserver/ting?format=json&callback=&from=webapp_music&method=baidu.ting.billboard.billList&type=1&size=10').then(
      res => {
        this.songList = res.data.song_list
        console.log(this.songList)
      }
    )
    this.audioCtx = wx.createAudioContext('myAudio')
  }
}
</script>
<style scoped>
.content-ft{
  height: 77.2vh;
}
.weui-tab__content{
  height:100%;
  overflow-y:scroll;
}
.music-list{
  position: relative;
  text-align: left;
  height:100%;
  overflow-y:scroll;
}
.album-title{
  position: relative;
  left: 10px;
}
.album-title::before{
  content: '-';
  position: absolute;
  top: 0;
  left: -10px;
}
.over-content{
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.iconfont {
  font-family:"iconfont" !important;
  font-size:18px;
  font-style:normal;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: red;
}
.fix-footer{
  position:fixed;
  bottom:0;
  height:auto;
  width:100vw;
  background:rgba(255,255,255,1);
}
/* #myAudio{
  width: 10vw;
} */
.weui-media-box {
position:relative;
padding: 0;
}

</style>
