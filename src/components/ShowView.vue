<template>
  <!--这个实际是要接收的数据-->
  <!--ShowView相对于app来说是子组件，所以-->
  <!--ShowView组件中获取网络数据，然后塞给它的字组件-->
  <div class="showView">
    <BlogItem
      v-for="item in listArr"
      :key="item.title"
      :mytitle="item.title"
      :mycontent="item.description"
      :mytime="item.posttime"
    ></BlogItem>
    <div class="pageGroup">
      <div class="btn" @click="pageDown">上一页</div>
      <div class="btn" @click="pageUp">下一页</div>
    </div>
  </div>
</template>
<script>
import BlogItem from './BlogItem.vue'
import axios from 'axios'
export default {
  /* 这个其实返回的是自己的数据，对于父组件来说就必须是使用return,但是对于他的子组件就可以直接使用 */
  data() {
    return {
      listArr: [],
      currentPage: 1
    }
  },
  components: {
    BlogItem
  },
  /* 组件生成之后，就可以向网络申请数据，存储到res.data */
  created() {
    this.getData()
  },
  methods: {
    getData() {
      axios({
        url: 'https://ku.qingnian8.com/dataApi/qingKu/getList.php',
        params: {
          /* page是看几页 */
          page: this.currentPage,
          /* 每页现实几个 */
          num: 9
        }
      }).then((res) => {
        console.log(res.data)
        this.listArr = res.data
      })
    },
    pageUp() {
      this.currentPage++
      console.log('pageup')
      this.getData()
      document.documentElement.scrollTop = 0
    },
    pageDown() {
      if (this.currentPage <= 1) {
        this.currentPage = 1
      } else {
        this.currentPage = this.currentPage - 1
      }
      this.getData()
    }
  }
}
</script>
<style lang="less">
.showView {
  padding: 60px 30px;
}
.pageGroup {
  padding: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.btn {
  border: 1px solid #41b883;
  padding: 10px 20px;
  color: #41b883;
  font-size: 18px;
  margin: 0 10px;
  cursor: pointer;
}
</style>
