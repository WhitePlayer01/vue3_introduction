<template>
  <div class="image-text-component">
    <div class="image-content">
      <img src="@/assert/text_image/1.jpg" alt="Sample Image" />
    </div>
    <div class="text-content">
      <h3>Text Section</h3>
      <p>This is the text section of the component.</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ImageTextComponent'
}
</script>

<style scoped>
.image-text-component {
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

.image-content {
  width: 40%;
  background-color: #e6f7ff; /* Light cyan background */
  padding: 10px;
  border-radius: 8px;
}

.image-content img {
  width: 100%;
  height: auto;
  border-radius: 8px;
  object-fit: cover; /* Ensure the image covers the container without distortion */
  object-position: center; /* Center the image within the container */
}

.text-content {
  width: 60%;
  padding-left: 20px; /* Add padding between image and text */
  background-color: #fff; /* White background */
  padding: 10px;
  border-radius: 8px;
}
</style>
