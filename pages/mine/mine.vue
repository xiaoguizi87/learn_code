<template>
  <div class='container'>
    <open-data class='icon' mode='aspectFit' type='userAvatarUrl'></open-data>
    <!-- <button class='bt' type="info" @click='goto("/pages/study/index")'>学习园地</button> -->
<!--    <button class='bt' type="info" @click='goto("/pages/wrongbook/wrongbook")'>错题本</button>
    <button class='bt' type="info" @click='goto("/pages/log/log")'>学习记录</button> -->
    <button class='bt' plain type="primary" open-type='feedback'>意见反馈</button>
    <button class='bt' plain type="primary" @click='gotoOtherMiniProgram()'>趣学小学数学</button>
    <button class='shareBtn' open-type="share">分享</button>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        'openid': ''
      }
    },
    onLoad() {},
    methods: {
      showTips: function() {
        uni.showToast({
          title: '功能加速开发中', // 提示的内容,
          duration: 1000, // 延迟时间,
          mask: true // 显示透明蒙层，防止触摸穿透,
        })
      },
      goto: function(url) {
        uni.navigateTo({
          url
        })
      },
      gotoOtherMiniProgram: function() {
        console.log('begin jump')
        wx.navigateToMiniProgram({
          appId: 'wx9f2787d263ca3aae',
          path: 'pages/index/index',
          envVersion: 'release',
          success(res) {
            // 打开成功
            console.log('test')
          },
          fail(res) {
            console.log(res)
          }
        })
      }
    },
    onShareAppMessage: function(options) {
      console.log('分享的代码！！')
    }
  }
</script>
<style scoped>
  /**
*open-data 的头像做不了圆角
*这里是覆盖一个镂空的view在上面 镂空view的边界做成与周围背景颜色一样 做了伪圆角
**/

  .shareBtn {
    position: fixed;
    bottom: 150rpx;
    right: -5rpx;
    width: 120rpx;
    font-size: 10px;
    height: 60rpx;
    background: pink;
  }

  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    /* justify-content: space-between; */
    width: 100vw;
    height: 100vh;
    padding: 80rpx 0;
    box-sizing: border-box;
    background-size: 100% 100%;
  }

  .icon {
    height: 200rpx;
    width: 200rpx;
    border-radius: 50%;
    border: 1rpx solid #e9ee9d;
    overflow: hidden;
  }

  .bt {
    margin: 20rpx;
    width: 240rpx;
    height: 80rpx;
    font-size: 14px;
    /* width: 200rpx; */
  }
</style>
