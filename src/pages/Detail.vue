<template>
  <div class="detail">
    <common-header :title="title"></common-header>
    <detail-scroll-wrapper></detail-scroll-wrapper>
  </div>
</template>

<script>
import CommonHeader from 'components/Header/Common';
import DetailScrollWrapper from 'components/ScrollWrapper/Detail'
export default {
  name: 'Detail',
  components: {
    CommonHeader,
    DetailScrollWrapper,
  },
  data() {
    return {
      title: '详情',
    }
  }
}
</script>

<style lang="scss" scoped>
</style>