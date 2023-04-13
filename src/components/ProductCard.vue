<template>
  <div class="product-card">
   <router-link :to="{ name: 'ProductDetails', params: { id: product.id }}">
    <div class="product-image">
      <img :src="product.image" :alt="product.name">
    </div>
    <div class="product-info">
      <h2>{{ product.name }}</h2>
      <p class="price">{{ product.price | currency }}</p>
      <p>{{ product.description }}</p>
    </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'ProductCard',
  props: {
    product: {
      type: Object,
      required: true
    },
     props: ['product']
  },
  filters: {
    currency(value) {
      return `$${value.toFixed(2)}`;
    }
  }
}
</script>

<style>
.product-card {
  display: flex;
  flex-direction: column;
  width: 300px;
  border: 1px solid #ccc;
  border-radius: 4px;
  overflow: hidden;
}

.product-image img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.product-info {
  padding: 1rem;
}

.price {
  font-weight: bold;
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}
</style>
