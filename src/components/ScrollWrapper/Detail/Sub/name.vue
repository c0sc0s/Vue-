<template>
  <div class="name-bd">
    <span class="iconfont icon-name"></span>
    <span class="name-text">{{ name }}</span>
  </div>
</template>

<script>
export default {
  name: 'DetailName',
  props: {
    name: {
      type: String,
      default() {
        return '名称加载中'
      },
    },
  }
}
</script>

<style lang="scss" scoped>
.name-bd {
  display: flex;
  height: 0.44rem;
  padding: 0.03rem 0.15rem 0;
  border-bottom: 1px solid #ddd;
  line-height: 0.39rem;
  box-sizing: border-box;
  background: #fff;
  .icon-name {
    font-size: 0.18rem;
    color: #000;
  }

  .name-text {
    font-size: 0.14rem;
    margin-left: 0.1rem;
  }
}
</style>