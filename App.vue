<template>
  <div id="app">
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
    <h1>Hello Vue 3!</h1>
    <div class="carousel-wrapper" ref="carouselComponent">
      <VerticalCarousel />
    </div>
    <div class="next-component" ref="nextComponent">
      <CompanyProfile />
      <CardsAndTextBoxes />
      <TextImageComponent ref="textImageComponent" />
      <ImageTextComponent />
    </div>
  </div>
</template>

<script>
import CompanyProfile from './components/CompanyProfile.vue';
import CardsAndTextBoxes from './components/CardsAndTextBoxes.vue';
import HorizontalCarousel from './components/HorizontalCarousel.vue';
import VerticalCarousel from './components/VerticalCarousel.vue';
import TextImageComponent from './components/TextImageComponent.vue';
import ImageTextComponent from './components/ImageTextComponent.vue';

export default {
  name: 'App',
  components: {
    CompanyProfile,
    CardsAndTextBoxes,
    HorizontalCarousel,
    VerticalCarousel,
    TextImageComponent,
    ImageTextComponent
  },
  data() {
    return {
      lastScrollTop: 0
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
    this.observeTextImageComponent();
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      // ...existing code...
    },
    observeTextImageComponent() {
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            this.$refs.textImageComponent.$el.classList.add('fade-in');
            observer.unobserve(this.$refs.textImageComponent.$el);
          }
        });
      }, { threshold: 0.1 });

      observer.observe(this.$refs.textImageComponent.$el);
    }
  }
};
</script>

<style>
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #f7f7f7; /* Light blue background */
  padding: 0 20px; /* Add padding on both sides */
}

nav {
  background-color: #333;
  overflow: hidden;
  margin-bottom: 20px;
}

nav ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

nav ul li {
  float: left;
}

nav ul li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

nav ul li a:hover {
  background-color: #111;
}

.carousel-wrapper {
  height: 60vh; /* Set the height of the carousel wrapper to 60% of the viewport height */
  margin: 20px 0;
}

.next-component {
  margin-top: 20px;
}

#company-profile {
  margin: 20px;
  padding: 20px;
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 8px;
}

#company-profile h2 {
  color: #2c3e50;
}

#company-profile p {
  color: #555;
  line-height: 1.6;
}

.cards {
  display: flex;
  justify-content: space-around;
  margin: 20px 0;
}

.card {
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
  width: 30%;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.text-boxes {
  display: flex;
  justify-content: space-around;
  margin: 20px 0;
}

.text-box {
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
  width: 45%;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.fade-in {
  animation: fadeIn 2s ease-in-out;
}
</style>
