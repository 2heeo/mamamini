<template>
  <header class="doc-header">
    <h1 class="doc-title">
      <NuxtLink to="/" class="link_home">MAMAmini</NuxtLink>
    </h1>

    <nav id="gnbContent" class="doc-gnb"> <!-- gnbContent 메뉴 바로가기 링크 -->
      <h2 class="screen_out">마마미니 메인메뉴</h2>
      <ul class="gnb_mamamini">
        <li><NuxtLink to="/intro">소개</NuxtLink></li>
        <li><NuxtLink to="/cafe">카페</NuxtLink></li>
        <li><NuxtLink to="/miniature">미니어쳐</NuxtLink></li>
        <li><NuxtLink to="/accommodation">숙박</NuxtLink></li>
        <li><NuxtLink to="/location">오시는 길</NuxtLink></li>
      </ul>
    </nav>
  </header>
</template>
