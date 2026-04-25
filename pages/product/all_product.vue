<template>
  <div>
    <h1>Welcome to All Product</h1>
    <!-- step 1 -->
    <!-- <ul>
      <li v-for="product in data.products" :key="product.id">
        {{ product.title }}
      </li>  
    </ul> -->
    <!-- step 2 -->
    <div class="product-grid">
      <NuxtLink class="container" :to="`/product/${product.id}`" v-for="product in data.products" :key="product.id">
        <h2 class="title">{{ product.title }}</h2>
        <img :src="product.thumbnail" alt="Product Image">
        <p>{{ product.description }}</p>
        <p>Price: {{ product.price }}</p>
      </NuxtLink>
    </div>
  </div>
</template>

<script setup>
const {data: data} = await useFetch('https://dummyjson.com/products?limit=5')
console.log(data);
</script>

<style scoped>
.product-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 30px;
  padding: 30px;
}
.container {
  background: #fff;
  padding: 15px;
  text-decoration: none;
  border-radius: 12px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}
.title {
  color: black;
  text-align: center;
  font-size: 1.2em;
}

.container:hover{
  background: rgb(255, 222, 160);
}

img {
  width: 200px;
  height: auto;
}
</style>