<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banners="banners"/>
    <home-recommand-view :recommends="recommends"/>
    <home-feature-view/>
    <tab-control class="tab-control" :titles="['流行','新款','精选']"/>
    <span>123</span>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
  </div>
</template>

<script>
import NavBar from "@/components/common/navbar/NavBar";
import TabControl from "@/components/content/TabControl/TabControl";

import HomeSwiper from "@/views/home/childComps/HomeSwiper";
import HomeRecommandView from "@/views/home/childComps/HomeRecommandView";
import HomeFeatureView from "@/views/home/childComps/HomeFeatureView";

import {getHomeMultidata} from "@/network/home";




export default {
  name: "Home",
  data() {
    return {
      banners: [],
      recommends: []
    }
  },
  components: {
    NavBar,
    HomeSwiper,
    HomeRecommandView,
    HomeFeatureView,
    TabControl
  },
  created() {
    getHomeMultidata()
    .then(res => {
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    }).catch(err => {

    })
  }
}
</script>

<style scoped>
  #home {
    padding-top: 44px;
  }

  .home-nav {
    background-color: var(--color-tint);
    color: #fff;

    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    z-index: 9;
  }

  .tab-control {
    position: sticky;
    top: 44px;
  }
</style>
