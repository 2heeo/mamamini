<template>
  <footer class="doc-footer">
    <div class="inner_footer">
      <div class="cont_fnb">
        <h2 class="screen_out">하단메뉴</h2>
        <ul class="doc-fnb">
          <li><NuxtLink class="link_fnb">더미더미더미</NuxtLink></li>
          <li><NuxtLink class="link_fnb">더미더미더미</NuxtLink></li>
          <li><NuxtLink class="link_fnb">더미더미더미</NuxtLink></li>
          <li><NuxtLink class="link_fnb">더미더미더미</NuxtLink></li>
          <li><NuxtLink class="link_fnb">더미더미더미</NuxtLink></li>
        </ul>
        <ul class="list_sns">
          <li><NuxtLink :to="snsData.blogHref" class="link_fnb"><span class="ico_mmn ico_blog">작가 블로그</span></NuxtLink></li>
          <li>
            <span class="ico_mmn ico_insta">인스타그램</span>
            <ul class="list_insta">
              <li v-for="insta in snsData.instagram" :key="insta">
                <NuxtLink :to="insta.href" class="link_fnb">{{insta.title}}</NuxtLink>
              </li>
            </ul>
          </li>
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
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    padding: 20px 50px;
    background: $color-dark;
    box-sizing: border-box;
    .link_fnb {
        color: $color-white;
      }
    .cont_fnb {
      padding: 10px 0;
      @include clearfix;
    }
    .doc-fnb {
      float: left;
      @include clearfix;
      li {
        float: left;
        &+li {
          padding-left: 10px;
        }
      }
    }
    .list_sns {
      float: right;
      .list_insta {
        display: none;
        li {
          position: relative;
          float: left;
          margin-top: 8px;
          padding: 0 8px;
          &::before {
            position: absolute;
            top: 9px;
            left: 0;
            margin-right: 0 4px;
            width: 2px;
            height: 2px;
            background: $color-white;
            content: '';
          }
        }
      }
      &:hover {
        .list_insta { // todo-heeo. 어떻게 처리 할 것인가..
          display: block;
        }
      }
      @include clearfix;
      li {
        float: left;
        &+li {
          padding-left: 10px;
        }
      }      
    }
    small {
      display: block;
      padding: 20px;
      text-align: center;
      color: $color-white;
      border-top: 1px solid $color-white;
      box-sizing: border-box;
    }
  }
</style>