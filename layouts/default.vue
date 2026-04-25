<template>
    <div>
        <header>
          <nav>
              <h1 class="logo">My App</h1>
              <NuxtLink to="/">Home </NuxtLink>
              <NuxtLink to="/about">About </NuxtLink>
              <NuxtLink to="/product/all_product">All Product</NuxtLink>
          </nav>
      </header>
      <div>
        <slot></slot>
      </div>
    </div>
</template>

<script>
export default {

}
</script>

<style>
nav {
    margin: 10px auto;
    padding: 10px auto;
    justify-content: center;
    gap: 10px;
    align-items: center;
    background: #333;
    display: flex;
}
nav a{
    color: white;
    text-decoration: none;
    margin-left: px;
    font-size: 18px;
    padding: 10px;
}
nav a:hover {
    color: gold;
}

.logo {
    color: white;
    font-size: 24px;
    font-weight: bold;
    margin-right: auto;
    padding-left: 20px;
}
</style>