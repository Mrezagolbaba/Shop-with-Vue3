<template>
  <header>
    <nav>
      <router-link :to="{ name: 'home' }">Home</router-link>
      <router-link :to="{ name: 'cart' }">Cart</router-link>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style>
header {
  background-color: #333;
  color: #fff;
  padding: 1rem;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
