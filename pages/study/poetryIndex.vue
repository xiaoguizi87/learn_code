<template>
  <div class='content'>
    <u-parse :content="article" />
  </div>
</template>

<script>
  import uParse from '@/components/gaoyia-parse/parse.vue'
  import marked from 'marked'
  const poetry = require('./poetry')

  export default {
    components: {
      uParse
    },
    data() {
      return {
        article: '',
        id: 1
      }
    },
    onLoad() {
    	console.log(this.$mp.query)
    	let id = this.$mp.query.id
      let content = poetry.data[`poetry${id}`]
      console.log(content)
      this.article = marked(content)
    },
    methods: {
      preview(src, e) {
        // do something
      },
      navigate(href, e) {
        // do something
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
</style>
