<template>
  <Layout>
    <div class="home">
      <h1>Welcome to our shop!</h1>
      <div class="products-container">
        <div class="products">
          <ProductCard v-for="product in products" :key="product.id" :product="product" />
        </div>
      </div>
    </div>
  </Layout>
</template>

<script>
import Layout from '@/components/Layout.vue'
import ProductCard from '@/components/ProductCard.vue'
import productsData from '@/data/products.json'

export default {
  name: 'Home',
  components: {
    Layout,
    ProductCard
  },
  data() {
    return {
      products: productsData
    }
  }
}
</script>

<style>
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100%;
}

.products-container {
  height: calc(100% - 70px);
  overflow-y: scroll;
  display: flex;
  justify-content: center;
}

.products {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
  align-items: center;
}
</style>
