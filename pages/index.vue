<template xmlns:v-swiper="http://www.w3.org/1999/xhtml">
  <div id="root">
    <div id="header">
      <div class="hcontainer">
        <img
          src="https://i.loli.net/2019/03/15/5c8bae8aa5b71.png"
          style="height: 55px;"
        />
      </div>
    </div>
    <div id="swiper">
      <div v-swiper:mySwiper="swiperOption">
        <div class="swiper-wrapper">
          <div v-for="banner in banners" :key="banner" class="swiper-slide">
            <img :src="banner" style="max-height:100%; max-width:100%;" />
          </div>
        </div>
        <div slot="pagination" class="swiper-pagination"></div>
        <div slot="button-prev" class="swiper-button-prev"></div>
        <div slot="button-next" class="swiper-button-next"></div>
      </div>
    </div>
    <div id="content"></div>
  </div>
</template>

<script>
/* eslint-disable */
import '../assets/index.css'
export default {
  data() {
    return {
      banners: ['https://i.loli.net/2019/03/15/5c8bab7f7fe1f.jpg', 'https://i.loli.net/2019/03/15/5c8bab7f971db.jpg',
        'https://i.loli.net/2019/03/15/5c8bab7fd6daa.jpg'],
      swiperOption: {
        loop: true,
        slidesPerView: 'auto',
        centeredSlides: true,
        spaceBetween: 20,
        pagination: {
          el: '.swiper-pagination',
          type: 'progressbar'
        },
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      }
    }
  },
  mounted() {
  }
}
</script>

<style lang="scss" scoped>
.my-swiper {
  height: 300px;
  width: 100%;
  .swiper-slide {
    text-align: center;
    font-size: 38px;
    font-weight: 700;
    background-color: #eee;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .swiper-pagination {
    > .swiper-pagination-bullet {
      background-color: red;
    }
  }
}
</style>
