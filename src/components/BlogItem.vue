<template>
  <div class='itembox'>
    <div class='top'>
      <h2>这{{ mytitle }}</h2>
      <div class='time'>{{mytime}}</div>
    </div>
    <div class='content'>
      {{ mycontent }}
    </div>
    <div class='info'>
      <div class='list'>
        所属分类
        <span>所属标签</span>
      </div>
      <div class='author'>
        作者：
        <span>张三</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    mytitle: {
      type: String,
      default: ''
    },
    mycontent: {
      type: String,
      default: '没有任何内容'
    },
    mytime: {
      type: String,
      default: '神秘的发布时间'
    }
  }
}
</script>

<style lang="less">
.itembox {
  padding: 30px 0px;
  .top {
    display: flex;
    justify-content: space-between;
    padding-bottom: 10px;
    h2 {
      font-size: 25px;
      color: #333;
      width: 750px;
    }
    .time {
      font-size: 14px;
      color: #888;
    }
  }
  .content {
    background: #f6f6f6;
    border-radius: 5px;
    padding: 15px 10px;
    font-size: 18px;
    line-height: 1.8em;
    color: #444;
    margin-bottom: 10px;
  }
  .info {
    display: flex;
    justify-content: space-between;
    font-size: 14px;
    color: #888;
    span {
      font-size: 16px;
      color: #666;
    }
  }
}
</style>
