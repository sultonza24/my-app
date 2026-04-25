<template>
  <div class="container">
    <h1>Your journey starts here.</h1>
    <img src="/image/shopping.png" alt="Shopping">
    <h3>all product</h3>
  </div>
</template>

<script setup>
useHead({
    title: 'Home Page',
    meta: [
        { name: 'description', content: 'shopping page' }
    ]
})
const {data: data} = await useFetch('https://dummyjson.com/products')
console.log(data);
</script>
<style>
.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
img{
    width: 800px;
    height: auto;
    margin-top: 20px;
}

</style>