<template>
    <div class="container">
        <h1>Welcome to Nuxt.js</h1>
        <p>
        This  page is rendered on the server and then hydrated onthe client. You can edit this page to get started.
        </p>
        <img src="/public/image/chanel.png" alt="">
    </div>
</template>

<script>
export default {

}
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