<template>
  <div class="title-bd">
    <h1>
      <span :class="['iconfont', icon]"></span>
      <span class="title">{{ title }}</span>
    </h1>
  </div>
</template>

<script>
export default {
  name: 'DetailTitle',
  props: {
    icon: String,
    title: String,
  }
}
</script>

<style lang="scss" scoped>
@import "~styles/variables.scss";

.title-bd {
  display: flex;
  align-items: center;
  height: 0.44rem;
  padding: 0 0.15rem;
  border-bottom: 1px solid #ddd;
  line-height: 0.44rem;
  box-sizing: border-box;
  background: #fff;
  .iconfont {
    font-size: 0.18rem;
    color: $defaultGreen;
  }

  .title {
    font-size: 0.18rem;
    margin-left: 0.1rem;
    color: $defaultGreen;
  }
}
</style>