<template>
  <div class="company-profile">
    <section id="company-profile">
      <h2>About Our Company</h2>
      <p>We are a leading company in our industry, committed to providing top-quality products and services to our customers.</p>
      <p>Our mission is to innovate and lead the market with our cutting-edge solutions.</p>
    </section>
  </div>
</template>

<script>
export default {
  name: 'CompanyProfile'
}
</script>

<style scoped>
.company-profile {
  background-color: #f0f8ff; /* Light blue background */
  border-radius: 8px;
  padding: 20px;
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
</style>
