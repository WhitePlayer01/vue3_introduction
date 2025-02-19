<template>
  <div class="horizontal-carousel">
    <Carousel :itemsToShow="3" :autoplay="true" :autoplayTimeout="5000">
      <Slide v-for="(slide, index) in slides" :key="index">
        <img :src="slide.image" :alt="slide.title" />
      </Slide>
    </Carousel>
  </div>
</template>

<script>
import { Carousel, Slide } from 'vue3-carousel';

export default {
  name: 'HorizontalCarousel',
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
.horizontal-carousel {
  background-color: #f0f8ff; /* Light blue background */
  border-radius: 8px;
  overflow: hidden;
  padding: 20px;
}

.carousel-container {
  height: 200px; /* Set the height of the container to 200px */
}

.VueCarousel {
  height: 100%; /* Set the height of the carousel to 100% of the container height */
}

.VueCarousel-slide {
  height: 100%; /* Set the height of each slide to 100% */
  display: flex;
  align-items: center;
  justify-content: center;
}

.VueCarousel-slide img {
  height: 100%; /* Ensure the image covers the entire slide height */
  width: 100%; /* Ensure the image covers the entire slide width */
  object-fit: cover; /* Ensure the image covers the slide area without distortion */
}
</style>
