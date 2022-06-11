<template>
  <section class="inner-main">
    <h2 class="screen_out">카페 소개 본문</h2>
    <article id="mainContent" class="content-article">
      <h3 class="screen_out">카페 소개 본문 상세</h3>
      <div class="cont_intro">
        <strong class="tit_menu">카페 소개</strong>
        <div class="cont_">
          <div class="wrap_">
            <img src="@/static/img_cafe.jpeg" class="img_cafe" alt="">
            <img src="@/static/img_cafe2.jpeg" class="img_cafe" alt="">
          </div>
          <div class="wrap_">
            <img src="@/static/img_cafe1.jpeg" class="img_cafe" alt="">
          </div>
        </div>
      </div>
      <div class="cont_menu">
        <strong class="tit_menu">메뉴</strong>
        <Carousel2Column/>
      </div>
    </article>
  </section>
</template>

<style lang="scss" scoped>
  .cont_menu {
    padding: 100px 0;
    background: $color-bg;
    box-sizing: border-box;
  }
  .tit_menu {
    display: block;
    margin-bottom: 50px;
    color: $color-dark;
    font-size: 36px;
    text-align: center;
  }
  .cont_ {
    display: flex;
    margin: 0 auto;
    width: 1200px;
    justify-content: space-between;
  }

  .wrap_ {
    flex: 1;
    width: 50%;
  }
  .img_cafe {
    width: 100%;
  }
</style>