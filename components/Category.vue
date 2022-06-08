<template>
  <div class="cont_category">
    <strong class="tit_service">서비스</strong>
    <div class="wrap_category">
      <div class="item_category" v-for="category in categories" :key="category.title">
        <strong class="tit_category" v-html="category.title"/>
        <div class="bg_category" :style="{'background-image':'url(' + category.img +')'}"></div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Category',
    data() {
      return {
        categories: [
          {
            title: '카페',
            img: 'static/img_cafe.jpeg'
          },
          {
            title: '미니어쳐',
            img: 'static/img_miniature.jpeg'
          },
          {
            title: '숙소',
            img: 'static/img_accomm.jpeg'
          }
        ]
      }
    }
  }
</script>

<style lang="scss" scoped>
  .cont_category {
    padding: 100px 0;
    text-align: center;
    .tit_service {
      display: block;
      padding: 50px 0;
      color: $color-dark;
      font-size: 40px;
      font-weight: 700;
      font-family: NotoSansKR;
    }
  }
  .wrap_category {
    margin: 0 auto;
    width: 1300px;
    @include clearfix;
  }
  .item_category {
    overflow: hidden;
    position: relative;
    float: left;
    width: 400px;
    height: 500px;
    text-align: center;
    background: $color-white;
    border-radius: 15px;
    box-shadow: 4px 12px 30px 6px rgb(0 0 0 / 9%);
    box-sizing: border-box;
    &+.item_category {
      margin-left: 50px;
    }

    .tit_category {
      display: block;
      padding: 30px;
      font-size: 20px;
    }
    .bg_category {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 400px;
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
    }
  }
</style>