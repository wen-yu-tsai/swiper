<template>
  <!-- <div class="swiper-container"> -->
    <swiper
      v-if="slides.length > 0"
      :slides-per-view="4"
      :space-between="30"
      :centered-slides="true"
      :pagination="{ clickable: true }"
      :modules="modules"
      :breakpoints="{
        640: { slidesPerView: 2, spaceBetween: 20 },
        768: { slidesPerView: 3, spaceBetween: 25 },
        1024: { slidesPerView: 4, spaceBetween: 30 }
      }"
      class="mySwiper"
      @swiper="onSwiper"
    >
      <SlideItem
          v-for="slide in slides"
          :key="slide.id"
          :slide-data="slide"
        />
        <!-- 不要寫錯了 -->
    </swiper>
  <!-- </div> -->
</template>
<script>
  // Import Swiper Vue.js components
  import { Swiper } from 'swiper/vue';
  import SlideItem from "./components/SlideItem.vue"; //路徑要對，大小寫敏感

  // Import Swiper styles
  import 'swiper/css';

  import 'swiper/css/pagination';

  import './style.css';

  // import required modules
  import { Pagination } from 'swiper/modules';

  export default {
    name:"App",
    components: {
      Swiper,
      SlideItem,
    },
    setup() {
      //建立資料
      const slides = [
      { id: 1, imageUrl: 'https://picsum.photos/200/200?random=1', title: '圖片 1' },
      { id: 2, imageUrl: 'https://picsum.photos/200/200?random=2', title: '圖片 2' },
      { id: 3, imageUrl: 'https://picsum.photos/200/200?random=3', title: '圖片 3' },
      { id: 4, imageUrl: 'https://picsum.photos/200/200?random=4', title: '圖片 4' },
      { id: 5, imageUrl: 'https://picsum.photos/200/200?random=5', title: '圖片 5' },
      { id: 6, imageUrl: 'https://picsum.photos/200/200?random=6', title: '圖片 6' },
      { id: 7, imageUrl: 'https://picsum.photos/200/200?random=7', title: '圖片 7' },
      { id: 8, imageUrl: 'https://picsum.photos/200/200?random=8', title: '圖片 8' },
      { id: 9, imageUrl: 'https://picsum.photos/200/200?random=9', title: '圖片 9' },
      { id: 10, imageUrl: 'https://picsum.photos/200/200?random=10', title: '圖片 10' },
    ];

    const onSwiper = (swiper) => {
      console.log('Swiper initialized:', swiper);
    };

      return {
        modules: [Pagination],
        slides,//記得return 資料
        onSwiper,
      };
    },
  };
</script>
