<template>
  <div class="datetime-bd">
    <span class="iconfont icon-datetime"></span>
    <span class="datetime-text">{{ datetime }}</span>
  </div>
</template>

<script>
export default {
  name: 'DetailOpenDateTime',
  props: {
    datetime: {
      type: String,
      default() {
        return '加载中...'
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.datetime-bd {
  display: flex;
  align-items: center;
  min-height: 0.44rem;
  padding: 0.1rem 0.15rem;
  background-color: #fff;
  border-bottom: 1px solid #ddd;
  box-sizing: border-box;

  .icon-datetime {
    font-size: 0.18rem;
    margin-right: 0.1rem;
    color: #999;
  }

  .datetime-text {
    font-size: 0.14rem;
    line-height: 0.18rem;
  }
}
</style>