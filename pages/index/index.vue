<template>
  <view class="main">
    <text class="titleTxt">趣学小学语文</text>
    <button @click='goto("/pages/game/game")'>常识练习</button>
  </view>
</template>

<script>
  export default {
    data() {
      return {

      };
    },
    methods: {
      goto(url) {
        uni.navigateTo({
          url
        })
      }
    }
  }
</script>

<style lang="scss">
  .titleTxt {
    color: #ff5994;
    font-size: 40px;
    margin: 50rpx 0rpx;
  }

  .main {
    display: flex;
    flex-direction: column;
    align-items: center;
    /* justify-content: center; */
    // background: #cafedb;
    height: 100vh;
  }

  button {
    margin: 20upx 0;
    background: #edff8f;
    font-size: 24px;
    color: #12cbff;
    width: 70vw;
  }
</style>
