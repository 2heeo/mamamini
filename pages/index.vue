<template>
  <section class="inner-main">
    <h2 class="screen_out">메인 본문</h2>
    <article id="mainContent" class="content-article">
      <h3 class="screen_out">메인 본문 상세</h3>
      <div class="cont_top">
        <strong class=""></strong>
        <Carousel/>
      </div>
      <Category/>
      <Location/>
    </article>
  </section>
</template>

<script>
  export default {
    
  }
</script>

<style lang="scss" scoped>
  .cont_top {
    height: 100vh;
  }
</style>