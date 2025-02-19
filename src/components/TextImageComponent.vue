<template>
  <div>
    <div class="text-image-component">
      <div class="text-content">
        <h3>Text Section</h3>
        <p>This is the text section of the component.</p>
      </div>
      <div class="image-content">
        <img src="@/assert/text_image/1.jpg" alt="Sample Image" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TextImageComponent'
}
</script>

<style scoped>
.text-image-component {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin: 20px 0;
  padding: 20px;
  background-color: #f0f8ff; /* Light blue background */
}

.text-content {
  width: 40%;
  background-color: #fff; /* White background */
  padding: 10px;
  border-radius: 8px;
}

.image-content {
  width: 60%;
  position: relative;
  overflow: hidden;
  background-color: #e6f7ff; /* Light cyan background */
  border-radius: 8px;
}

.image-content img {
  width: 100%;
  height: auto;
  border-radius: 8px;
  object-fit: cover; /* Ensure the image covers the container without distortion */
  object-position: center; /* Center the image within the container */
  clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%); /* Diagonal crop for both top-left and bottom-left corners */
}
</style>
