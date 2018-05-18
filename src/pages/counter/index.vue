<!--// <template>
//   <div class="counter-warp">
//     <p>Vuex counter：{{ count }}</p>
//     <p>
//       <button @click="increment">+</button>
//       <button @click="decrement">-</button>
//     </p>
//     <input type="number" class="weui_input">
//     <i class="weui-loading weui-icon_toast"></i>
//     <a class="weui-btn weui-btn_mini weui-btn_default">按钮</a>  
//     <a href="/pages/index/main" class="home">去往首页</a>
 //     <a href="javascript:;" class="weui-btn weui-btn_primary">绿色按钮</a> 
//   </div>
// </template>

// <script>
// // Use Vuex
// import store from './store'

// export default {
//   computed: {
//     count () {
//       return store.state.count
//     }
//   },
//   methods: {
//     increment () {
//       store.commit('increment')
//     },
//     decrement () {
//       store.commit('decrement')
//     }
//   }
// }

// </script>
// <style>
// .counter-warp {
//   text-align: center;
//   margin-top: 100px;
// }
// .home {
//   display: inline-block;
//   margin: 100px auto;
//   padding: 5px 10px;
//   color: blue;
//   border: 1px solid blue;
// }

// </style>-->
<template>
  <div class="page">
    <div class="page__bd page__bd_spacing">
      <div class="weui-flex">
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
      </div>
      <div class="weui-flex">
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
      </div>
      <div class="weui-flex">
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
      </div>
      <div class="weui-flex">
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
      </div>
      <div class="weui-flex">
        <div>
          <div class="placeholder">weui</div>
        </div>
        <div class="weui-flex__item">
          <div class="placeholder">weui</div>
        </div>
        <div>
          <div class="placeholder">weui</div>
        </div>
      </div>
    </div>
    <div class="weui-footer">
      <div class="weui-footer__links">
        <navigator url="" class="weui-footer__link">底部链接</navigator>
        <navigator url="/pages/home/main" class="weui-footer__link">底部链接</navigator>
      </div>
      <div class="weui-footer__text">Copyright © 2008-2018 weui.io</div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  methods: {

  }

}
</script>

<style>
.placeholder {
  margin: 5px;
  padding: 0 10px;
  text-align: center;
  background-color: #ebebeb;
  height: 2.3em;
  line-height: 2.3em;
  color: #cfcfcf;
}
</style>