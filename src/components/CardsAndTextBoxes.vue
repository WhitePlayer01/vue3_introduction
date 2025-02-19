<template>
  <div class="cards-and-text-boxes" ref="scrollContainer">
    <div class="cards">
      <div class="card">
        <img :src="require('../assert/card_image/1.jpg')" alt="Card 1 Image" class="card-image" />
        <h3>Card 1</h3>
        <p>This is a description for card 1.</p>
      </div>
      <div class="card">
        <img :src="require('../assert/card_image/2.jpg')" alt="Card 2 Image" class="card-image" />
        <h3>Card 2</h3>
        <p>This is a description for card 2.</p>
      </div>
      <div class="card">
        <img :src="require('../assert/card_image/3.jpg')" alt="Card 3 Image" class="card-image" />
        <h3>Card 3</h3>
        <p>This is a description for card 3.</p>
      </div>
    </div>
    <div class="text-boxes">
      <div class="text-box">
        <img :src="require('../assert/card_image/1.jpg')" alt="Text Box 1 Image" class="text-box-image" />
        <h3>Text Box 1</h3>
        <p>This is some text for text box 1.</p>
      </div>
      <div class="text-box">
        <img :src="require('../assert/card_image/2.jpg')" alt="Text Box 2 Image" class="text-box-image" />
        <h3>Text Box 2</h3>
        <p>This is some text for text box 2.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardsAndTextBoxes',
  data() {
    return {
      scrollDirection: 1 // 1 for forward, -1 for backward
    };
  },
  mounted() {
    this.startAutoScroll();
  },
  beforeDestroy() {
    this.stopAutoScroll();
  },
  methods: {
    startAutoScroll() {
      this.scrollInterval = setInterval(() => {
        const container = this.$refs.scrollContainer;
        if (this.scrollDirection === 1 && container.scrollLeft + container.clientWidth >= container.scrollWidth) {
          this.scrollDirection = -1;
        } else if (this.scrollDirection === -1 && container.scrollLeft <= 0) {
          this.scrollDirection = 1;
        }
        container.scrollLeft += this.scrollDirection;
      }, 20); // Adjust the speed as needed
    },
    stopAutoScroll() {
      clearInterval(this.scrollInterval);
    }
  }
}
</script>

<style scoped>
.cards-and-text-boxes {
  overflow-x: auto; /* Enable horizontal scrolling */
  white-space: nowrap; /* Prevent line breaks */
  scrollbar-width: none; /* Hide scrollbar for Firefox */
  -ms-overflow-style: none; /* Hide scrollbar for Internet Explorer and Edge */
}

.cards-and-text-boxes::-webkit-scrollbar {
  display: none; /* Hide scrollbar for Chrome, Safari, and Opera */
}

.card, .text-box {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  background-color: #fff; /* White background */
  border-radius: 8px;
  padding: 20px;
}

.card:hover, .text-box:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.cards {
  display: flex;
  justify-content: space-around;
  margin: 20px 0;
}

.card {
  background-color: #e6f7ff; /* Light cyan background */
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
  width: 30%;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin: 0 10px; /* Add spacing between cards */
  display: inline-block; /* Ensure cards are inline for horizontal scrolling */
  word-wrap: break-word; /* Allow text to wrap */
  overflow-wrap: break-word; /* Allow text to wrap */
}

.card p {
  word-wrap: break-word; /* Allow text to wrap */
  overflow-wrap: break-word; /* Allow text to wrap */
  white-space: normal; /* Ensure text wraps within the card */
}

.card-image {
  width: 100%;
  height: auto;
  border-radius: 8px 8px 0 0;
}

.text-boxes {
  display: flex;
  justify-content: space-around;
  margin: 20px 0;
}

.text-box {
  background-color: #f0f8ff; /* Light blue background */
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
  width: 45%;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin: 0 10px; /* Add spacing between text boxes */
  display: inline-block; /* Ensure text boxes are inline for horizontal scrolling */
}

.text-box p {
  word-wrap: break-word; /* Allow text to wrap */
  overflow-wrap: break-word; /* Allow text to wrap */
  white-space: normal; /* Ensure text wraps within the text box */
}

.text-box-image {
  width: 100%;
  height: auto;
  border-radius: 8px 8px 0 0;
}
</style>
