<template>
  <Layout>
     <div class="product-details">
    <div class="image-container">
      <img :src="product.image" alt="Product Image" />
    </div>
    <div class="product-info">
      <h1>{{ product.name }}</h1>
      <p>{{ product.description }}</p>
      <p>Price: {{ product.price }} $</p>
      <button @click="addToCart">Add to Cart</button>
    </div>
  </div>
  </Layout>
</template>

<script>
import Layout from '@/components/Layout.vue'
import productsData from '@/data/products.json'

export default {
  name: 'ProductDetails',
  components: {
    Layout
  },
  data() {
    return {
      product: null
    }
  },
  created() {
    const productId = parseInt(this.$route.params.id)
    this.product = productsData.find(product => product.id === productId)
  }
}
</script>

<style>
.product-details {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.image-container {
  width: 300px;
  height: 300px;
  margin-bottom: 1rem;
  overflow: hidden;
}

.image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.product-info {
  width: 100%;
  max-width: 600px;
  text-align: center;
}

.product-info h1 {
  margin-bottom: 0.5rem;
}

.product-info p {
  margin-bottom: 1rem;
}

button {
  padding: 0.5rem 1rem;
  border: none;
  background-color: #555;
  color: #fff;
  cursor: pointer;
  transition: all 0.3s ease;
}

button:hover {
  background-color: #333;
}
</style>