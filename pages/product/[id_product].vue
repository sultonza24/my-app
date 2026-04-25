<template>
  <div class="page">
    <Head>
      <Title>My app | {{ product.title }}</Title>
      <Meta name="description" :content="product.description"/>
    </Head>
    <NuxtLink to="/product/all_product" class="back-btn">← Back to Products</NuxtLink>
    <div class="card">
      <img :src="product.thumbnail" alt="Product Image" class="product-img">
      <div class="info">
        <h1 class="product-title">{{ product.title }}</h1>
        <span class="category">{{ product.category }}</span>
        <p class="description">{{ product.description }}</p>
        <div class="price">${{ product.price }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
// import { useRoute } from 'vue-router'
// แบบเต็ม
const route = useRoute()
const id_product = route.params.id_product
// แบบย่อ
// const { params } = useRoute().params.id_product

const {data: product} = await useFetch(`https://dummyjson.com/products/${id_product}`)
console.log(product);

</script>


<style scoped>
.page {
  max-width: 900px;
  margin: 40px auto;
  padding: 0 20px;
  font-family: sans-serif;
}

.back-btn {
  display: inline-block;
  margin-bottom: 24px;
  color: #555;
  text-decoration: none;
  font-size: 0.95em;
}

.back-btn:hover {
  color: #000;
}

.card {
  display: flex;
  gap: 40px;
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  padding: 30px;
}

.product-img {
  width: 280px;
  height: 280px;
  object-fit: contain;
  border-radius: 8px;
  background: #f5f5f5;
  flex-shrink: 0;
}

.info {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.product-title {
  font-size: 1.6em;
  font-weight: 700;
  color: #222;
  margin: 0;
}

.category {
  display: inline-block;
  background: #ffe0a0;
  color: #b06000;
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 0.85em;
  font-weight: 600;
  text-transform: capitalize;
}

.description {
  color: #555;
  line-height: 1.6;
  margin: 0;
}

.price {
  font-size: 1.8em;
  font-weight: 700;
  color: #e67e00;
}
</style>