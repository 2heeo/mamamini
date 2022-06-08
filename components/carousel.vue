<template>
  <div class="wrap_carousel"></div>
</template>

<script>
  export default {
    name: 'Carousel'
  }
</script>

<style lang="scss" scoped>
  .wrap_carousel {
    height: 100%;
    background-image: url('@/static/img_carousel1.jpeg');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: bottom center;
  }
</style>