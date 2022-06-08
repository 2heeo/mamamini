<template>
  <header class="doc-header">
    <h1 class="doc-title">
      <NuxtLink to="/" class="link_home">MAMAmini</NuxtLink>
    </h1>
    <nav id="gnbContent" class="doc-gnb"> <!-- gnbContent 메뉴 바로가기 링크 -->
      <h2 class="screen_out">마마미니 메인메뉴</h2>
      <ul class="gnb_mamamini">
        <li><NuxtLink to="/intro" class="link_menu">소개</NuxtLink></li>
        <li><NuxtLink to="/cafe" class="link_menu">카페</NuxtLink></li>
        <li><NuxtLink to="/miniature" class="link_menu">미니어쳐</NuxtLink></li>
        <li><NuxtLink to="/accommodation" class="link_menu">숙박</NuxtLink></li>
      </ul>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
  .doc-header {
    z-index: 9999;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100px;
    padding: 0 40px;
    // background: $color-bg;
    box-sizing: border-box;
    @include clearfix;
    .doc-title {
      position: absolute;
      top: 0;
      left: 0;
      display: table;
      height: 100%;
      .link_home {
        display: table-cell;
        padding: 0 60px;
        // font-family: 'Roboto';
        font-weight: 400;
        color: $color-white;
        vertical-align: middle;
      }
    }
    .doc-gnb {
      position: absolute;
      top: 0;
      right: 0;
      height: 100%;
      display: table;
    }
    .gnb_mamamini {
      display: table-cell;
      vertical-align: middle;
      @include clearfix;
      li {
        float: left;
        margin-right: 40px;
        &:hover {
          margin-bottom: -3px;
          border-bottom: 3px solid $color-point;
        }
      }
      .link_menu {
        position: relative;
        color: $color-white;
        font-weight: 400;
        font-size: 20px;
        &:hover {
          color: $color-point;
        }
      }
    }
  }
  
</style>
