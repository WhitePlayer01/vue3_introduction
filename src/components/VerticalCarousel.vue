<template>
    <!-- 添加外层容器控制最大尺寸 -->
    <div class="carousel-wrapper vertical-carousel">
      <div class="carousel-container">
        <Carousel :itemsToShow="1" :autoplay="3000" :wrapAround="true">
          <Slide v-for="(slide, index) in slides" :key="index">
            <!-- 图片容器 -->
            <div class="slide-content">
              <img :src="slide.image" :alt="slide.title" />
            </div>
          </Slide>
        </Carousel>
      </div>
    </div>
  </template>
  
  <script>
  import { Carousel, Slide } from 'vue3-carousel';
  
  export default {
    name: 'VerticalCarousel',
    components: {
      Carousel,
      Slide
    },
    data() {
      return {
        slides: [
          { image: require('../assert/carousel_picture/1.jpg'), title: 'Slide 1' },
          { image: require('../assert/carousel_picture/2.jpg'), title: 'Slide 2' },
          { image: require('../assert/carousel_picture/3.jpg'), title: 'Slide 3' }
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  /* 关键修复点 */
  .carousel-wrapper {
    /* 限制轮播图最大尺寸 */
    max-width: 100%; 
    margin: 0 auto;
    background-color: #f0f8ff; /* Light blue background */
    border-radius: 8px;
    overflow: hidden;
  }
  
  .carousel-container {
    height: 60vh !important; /* 强制固定高度为视口高度的60% */
    position: relative;
    overflow: hidden; /* 隐藏溢出内容 */
  }
  
  /* 修正类名：vue3-carousel 3.x+ 使用.carousel */
  .carousel {
    height: 100% !important; /* 覆盖组件默认高度 */
  }
  
  /* 幻灯片容器 */
  .carousel__slide {
    height: 100% !important; /* 显式设置幻灯片高度 */
    padding: 0 !important; /* 清除默认padding */
  }
  
  /* 图片容器 */
  .slide-content {
    height: 100%;
    width: 100%;
    position: relative;
  }
  
  .slide-content img {
    height: 100%;
    width: 100%;
    object-fit: cover; /* 保持比例填充容器 */
    object-position: center; /* 图片居中显示 */
  }

  .vertical-carousel {
    border-radius: 8px; /* Add rounded corners */
    overflow: hidden; /* Ensure content respects the border radius */
  }
  </style>