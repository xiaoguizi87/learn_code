<template>
  <div class='content'>
    <button @click='goto("/pages/study/poetryIndex?id=1")'>《咏鹅》</button>
    <button @click='goto("/pages/study/poetryIndex?id=2")'>《咏柳》</button>
    <button @click='goto("/pages/study/poetryIndex?id=3")'>《登鹳雀楼》</button>
    <button @click='goto("/pages/study/poetryIndex?id=4")'>《春晓》</button>
    <button @click='goto("/pages/study/poetryIndex?id=5")'>《静夜思》</button>
  </div>
</template>

<script>
  export default {
    methods: {
      goto(url) {
        uni.navigateTo({
          url
        })
      }
    }
  }
</script>
<style>
  .content {
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
  
  button {
    min-width: 200rpx;
    margin: 50rpx;
  }
</style>
