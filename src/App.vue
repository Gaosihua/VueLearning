<template>
  <div id="app">
    <HdView />
    <div class="main">
      <ShowView/>
    </div>
    <FooterView/>
  </div>
</template>
<script>
// @ is an alias to /src
import HdView from './components/HdView.vue'
import FooterView from './components/FooterView.vue'
import ShowView from './components/ShowView.vue'
export default {
  components: {
    HdView,
    FooterView,
    ShowView
  }
}
</script>
<style lang="less">
*{ padding: 0;
    margin: 0;
    font-family: "微软雅黑";
    box-sizing: border-box;}
a{text-decoration: none;}
ul,ol{list-style: none;}
#app{
  width: 1200px;
  border: 1px solid #41b883;
  margin: 0 auto;
}
.main{
  min-height: 200px;
}
</style>
