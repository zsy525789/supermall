<template>
  <swiper>
    <swiper-item v-for="v in banners">
      <a :href="v.link"><img :src="v.image" alt=""></a>
    </swiper-item>
  </swiper>
</template>

<script>
import {Swiper,SwiperItem} from "@/components/common/swiper";
import NavBar from "@/components/common/navbar/NavBar";

export default {
  name: "HomeSwiper",
  props: {
    banners: {
      type: Array,
      default(){
        return [];
      }
    }
  },
  components: {
    Swiper,
    SwiperItem
  }
}
</script>

<style scoped>

</style>
