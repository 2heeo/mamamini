<template>
  <div>
    <div class="direct-link">
      <a href="#mainContent">본문 바로가기</a>
      <a href="#gnbContent">메뉴 바로가기</a>
    </div>
    <div class="container-doc">
      <NuxtLayout name="header"/>
      <main class="doc-main">
        <NuxtPage /> <!-- pages의 index.vue -->
      </main>
      <NuxtLayout name="footer"/>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .container-doc {
    position: relative;
    overflow: hidden;
  }
</style>