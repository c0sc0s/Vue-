<template>
  <div class="search-input">
    <div class="input-wrapper">
      <span class="iconfont icon-header-search"></span>
      <input
        type="text"
        class="input"
        v-model="keyword"
        :placeholder="placeholder"
        @input="onSearch"
      />
    </div>
  </div>
</template>

<script>
import tools from 'utils/tools';
import { SearchModel } from 'models/search';
import { mapState } from 'vuex';

export default {
  name: 'SearchInput',
  computed: {
    ...mapState(['cityId']),
  },
  data() {
    return {
      keyword: '',
      placeholder: '美食 / 景点 / 酒店 / 按摩 / KTV'
    }
  },
  methods: {
    onSearch: tools.throttle(function () {
      const keyword = tools.trimSpace(this.keyword);
      if (keyword.length <= 0) {
        this.$emit('onSearch', {});
        return;
      };


      const searchModel = new SearchModel();
      searchModel.searchAction(keyword, this.cityId).then(res => {
        this.$emit('onSearch', res);
      })
    }, 500)
  }
}
</script>

<style lang="scss" scoped>
.search-input {
  height: 0.44rem;
  padding: 0.06rem 0.15rem;
  background: #fff;
  box-sizing: border-box;

  .input-wrapper {
    position: relative;
    height: 100%;
    width: 100%;

    .iconfont {
      position: absolute;
      top: 0.08rem;
      left: 0.08rem;
      font-size: 0.16rem;
    }

    .input {
      width: 100%;
      height: 100%;
      border: 1px solid #ddd;
      border-radius: 0.03rem;
      box-sizing: border-box;
      font-size: 0.14rem;
      text-indent: 0.32rem;
    }
  }
}
</style>