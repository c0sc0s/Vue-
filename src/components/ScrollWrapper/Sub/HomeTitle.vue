<template>
  <div class="home-title">
    <p>{{ title }}</p>
  </div>
</template>

<script>
export default {
  name: 'HomeTitle',
  props: {
    title: {
      type: String,
      default() {
        return '一线生活通'
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.home-title {
  display: flex;
  align-items: center;
  height: 0.5rem;
  margin-top: 0.1rem;
  padding-left: 0.15rem;
  background-color: #fff;
  border-bottom: 1px solid #ddd;
  box-sizing: border-box;

  p {
    font-size: 0.18rem;
    color: #000;
  }
}
</style>