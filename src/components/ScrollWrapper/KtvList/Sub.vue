<template>
  <div class="ktv-item">
    <router-link
      :to="{
        path: '/detail',
        query: {
          field: 'ktv',
          id: data.id,
        },
      }"
    >
      <div class="img">
        <img class="ktv-img" :src="data.img" :alt="data.name" />
      </div>
      <div class="info">
        <h1 class="title">{{ data.name }}</h1>
        <p class="stars">
          <stars :starNum="+data.star"></stars>
          <span class="score">{{ data.score }}分</span>
        </p>
        <div class="others">
          <span class="item">
            ￥<span class="price">{{ data.default_price }}</span> 起
          </span>
          <span class="item">{{ data.area }}</span>
        </div>
      </div>
    </router-link>
  </div>
</template>

<script>
import Stars from "../Sub/Stars.vue";
export default {
  name: "KtvListSub",
  props: {
    data: Object,
  },
  components: {
    Stars,
  }
}
</script>

<style lang="scss" scoped>
@import "~styles/mixins.scss";
@import "~styles/variables.scss";
.ktv-item {
  position: relative;
  border-bottom: 1px solid #ddd;
  background-color: #fff;

  .img {
    width: 1.2rem;
    height: 1.2rem;
    padding: 0.1rem;
    box-sizing: border-box;

    .ktv-img {
      width: 100%;
      height: 100%;
    }
  }

  .info {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    padding: 0.1rem 0.1rem 0 1.2rem;
    box-sizing: border-box;

    .title {
      @include ellipsis;
      font-size: 0.18rem;
      color: #000;
      line-height: 0.2rem;
    }

    .stars {
      font-size: 0.14rem;
      line-height: 0.5rem;

      .score {
        color: $starColor;
      }
    }

    .others {
      display: flex;
      justify-content: space-between;
      font-size: 0.14rem;
      line-height: 0.35rem;

      &:nth-child(1) {
        color: $defaultOrange;
      }

      .price {
        font-size: 0.2rem;
        color: $defaultGreen;
      }
    }
  }
}
</style>