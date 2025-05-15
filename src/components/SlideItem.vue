<template>
  <swiper-slide class="slide-item">
    <img :src="slideData.imageUrl" :alt="slideData.title" class="slide-image" />
    <h3>{{ slideData.title }}</h3>
  </swiper-slide>
</template>

<script>
import { SwiperSlide } from 'swiper/vue';

export default {
  name: 'SlideItem',
  components: {
    SwiperSlide,
  },
  props: {
    slideData: {
      type: Object,
      required: true,
      default: () => ({
        imageUrl: '',
        title: '',
      }),
    },
  },
};
</script>

<style scoped>
.slide-item {
  text-align: center;
  font-size: 18px;
  background: #fff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  /* width: 200px*/
  height: 200px;
  min-width:200px;
  border: 1px solid purple; /* 診斷用邊框 */
}

.slide-image {
  width: 100%;
  height: 80%;
  object-fit: cover;
  border:1px solid black
}

h3 {
  margin: 10px 0 0;
  font-size: 16px;
  color:black
}
</style>