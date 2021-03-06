<template>
<div id="home">
  <NavBar class="home-nav">
    <div slot="center">购物街</div>
  </NavBar>
  <HomeSwiper :banners = banners />
  <RecommendView :recommends = recommends />
  <FeatureView />
</div>
</template>

<script>
  import NavBar from "components/common/navbar/NavBar"
  import HomeSwiper from "./childComps/HomeSwiper"
  import RecommendView from "./childComps/RecommendView"
  import FeatureView from "./childComps/FeatureView"
  import { getHomeMultidata } from "network/home"
  export default {
    name: "Home",
    components: {
      NavBar,
      HomeSwiper,
      RecommendView,
      FeatureView
    },
    data() {
      return {
        banners: [],
        recommends: []
      }
    },
    created() {
      getHomeMultidata().then(res => {
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list
      })
    }
  }
</script>

<style scoped>
  #home {
    padding-top: 44px;
  }
  .home-nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    color: #fff;
    background-color: var(--color-tint);
    z-index: 99;
  }
</style>
