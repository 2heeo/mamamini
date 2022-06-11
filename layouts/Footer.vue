<template>
  <footer class="doc-footer">
    <div class="inner_footer">
      <div class="cont_fnb">
        <h2 class="screen_out">하단메뉴</h2>
        <ul class="doc-fnb">
          <li>
            <span class="ico_mmn ico_blog"></span>
            <div class="wrap_sns">
              <NuxtLink :to="snsData.blogHref" class="link_fnb">작가 블로그</NuxtLink>
            </div>
          </li>
          <li>
            <span class="ico_mmn ico_insta">인스타그램</span>
            <div class="wrap_sns">
              <NuxtLink :to="insta.href" v-for="insta in snsData.instagram" :key="insta" class="link_fnb">{{insta.title}}</NuxtLink>
            </div>
          </li>
        </ul>
        <ul class="info_place">
          <li><span class="ico_mmn ico_wifi"></span><span class="txt_cv">와이파이존</span></li>
          <li><span class="ico_mmn ico_kids"></span><span class="txt_cv">예스키즈존</span></li>
          <li><span class="ico_mmn ico_parking"></span><span class="txt_cv">주차가능</span></li>
          <li><span class="ico_mmn ico_wc"></span><span class="txt_cv">남녀 구분 화장실</span></li>
          <li><span class="ico_mmn ico_pet"></span><span class="txt_cv">애견동반</span></li>
        </ul>
      </div>
      <small>&copy;MAMAmini. All rights reserved.</small>
    </div>

  </footer>
</template>

<script>
  export default {
    name: 'Footer',
    data() {
      return {
        snsData: {
          blogHref: '://blog.naver.com/jrdolgoong',
          instagram: [
            {
              title: '마마미니 작품',
              href: '://www.instagram.com/mamamini_jeju/'
            },
            {
              title: '마마미니 카페',
              href: '://www.instagram.com/mamamini_cafe/'
            },
            {
              title: '월드미니 작품',
              href: '://www.instagram.com/worldmini_jeju/'
            }
          ]
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
  .doc-footer {
    padding: 30px 50px;
    background: $color-dark;
    box-sizing: border-box;
    .link_fnb {
      display: block;
      margin-top: 5px;
      color: $color-white;
    }
    .cont_fnb {
      margin-bottom: 20px;
      @include clearfix;
    }
    .doc-fnb {
      float: left;
      @include clearfix;
      .ico_mmn {
        float: left;
      }
      li {
        float: left;
        &+li {
          padding-left: 10px;
        }
      }
    }
    .wrap_sns {
      display: inline-block;
      margin-left: 10px;
      min-width: 120px;
    }
    .info_place {
      float: right;
      @include clearfix;
      li {
        float: left;
        &+li {
          padding-left: 10px;
        }
        &:hover { // todo-heeo. 에니메이션 효과
          .txt_cv {
            display: block;
          }
        }
        .txt_cv {
          display: none;
          color: $color-white;
        }    
      }
    }
    small {
      display: block;
      padding-top: 30px;
      text-align: center;
      color: $color-white;
      font-size: 16px;
      border-top: 1px solid $color-white;
      box-sizing: border-box;
    }
  }
</style>