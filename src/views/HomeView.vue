<template>
  <div>
    <div id="top">
      <swiper class="swiper" :slides-per-view="1" :space-between="50" @swiper="onSwiper" @slideChange="onSlideChange">
        <swiper-slide style="background-image:url(/portfolio_mjc/top1.jpg)" class="slide ">
          <div class="header">명지전문대 정보통신공학과 진용화</div>

        </swiper-slide>
        <swiper-slide style="background-image:url(/portfolio_mjc/top2.jpg)" class="slide">
          <div class="header">명지전문대 정보통신공학과 진용화</div>
        </swiper-slide>
        <swiper-slide style="background-image:url(/portfolio_mjc/top3.jpg)" class="slide">
          <div class="header">명지전문대 정보통신공학과 진용화</div>
        </swiper-slide>
      </swiper>
    </div>

    <div id="portfolio">
      <div class="header">포트폴리오</div>

      <div class="list">
        <div class="item" @click="movePage('/portfolio1')" data-aos="zoom-out-right"
          style="background-image:url(/portfolio_mjc/top2.jpg)"></div>
        <div class="item" data-aos="zoom-in-left" style="background-image:url(/top2.jpg)"></div>
        <div class="item" data-aos="fade-up" data-aos-duration="3000" style="background-image:url(/top2.jpg)"></div>
        <div class="item" data-aos="fade-right" data-aos-offset="300" data-aos-easing="ease-in-sine"
          style="background-image:url(/top2.jpg)"></div>
        <div class="item" data-aos="fade-right" data-aos-easing="ease-in-back" data-aos-delay="10000"
          style="background-image:url(/top2.jpg)"></div>
        <div class="item" style="background-image:url(/top2.jpg)"></div>
      </div>
    </div>

  </div>
</template>

<script>
import { defineComponent } from 'vue';

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';

import aos from "aos";

// Components
import HelloWorld from '../components/HelloWorld.vue';

export default defineComponent({
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log('slide change');
    };
    return {
      onSwiper,
      onSlideChange,
    };
  },
  mounted() {
    aos.init();
  },
  methods: {
    movePage(path) {
      this.$router.push(path);
    }
  },
  name: 'HomeView',
});
</script>
<style lang="less">
#top {
  height: 100vh;

  .swiper {
    height: 100vh;

    .slide {
      background-position: center center;
      background-size: cover;

      //헤더 가운데정렬
      .header {
        font-size: 60px;
        font-weight: 900;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;

      }
    }
  }
}

#portfolio {

  .header {
    text-align: center;
    font-size: 40px;

  }

  width:1000px;
  margin: 0 auto;

  .list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 10px;

    .item {
      width: 100%;
      background-position: center center;
      background-size: cover;
      aspect-ratio: 1/1;
      border-radius: 10px;


    }
  }
}
</style>