<template>
  <div class="comment-bd">
    <detail-title icon="icon-haoping" title="评论关键词"></detail-title>
    <div class="comment-keyword">
      <span
        class="keyword"
        v-for="(item, index) of commentKeyword"
        :key="index"
        >{{ item }}</span
      >
    </div>
  </div>
</template>

<script>
import DetailTitle from './Title';
export default {
  name: 'DetailCommentKeyword',
  components: {
    DetailTitle,
  },
  props: {
    commentKeyword: Array,
  }
}
</script>

<style lang="scss" scoped>
@import "~styles/variables.scss";
@import "~styles/mixins.scss";

.comment-bd {
  @include flex-column;
  margin-top: 0.1rem;
  background: #fff;
  box-sizing: border-box;

  .comment-keyword {
    @include flex-row;
    flex-wrap: wrap;
    padding: 0.1rem;
    font-size: 0.14rem;
    line-height: 0.18rem;
    box-sizing: border-box;

    .keyword {
      @include vh-center;
      height: 0.25rem;
      padding: 0.05rem;
      margin: 0 0.05rem 0.05rem 0;
      border: 1px solid $defaultGreen;
      border-radius: 0.03rem;
      color: $defaultGreen;
    }
  }
}
</style>