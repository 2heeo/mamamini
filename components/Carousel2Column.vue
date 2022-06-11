<template>
  <div class="cont_carousel">
    <div class="wrap_item">
      <div ref="wrapImgs" class="wrap_imgs"
        :style="{width: `${500 * (carousels.length)}px`}">
        <div v-for="carousel in carousels" :key="carousel" class="wrap_img">
          <img class="tit_img" :class="carousel.class" :src="carousel.imgTitle" alt="">
          <img class="img_item" :src="carousel.src" alt="">
        </div>
      </div>
    </div>
    <div class="wrap_item">
      <div ref="wrapInfos" class="wrap_infos"
        :style="{width: `${500 * (carousels.length)}px`}">
        <div v-for="carousel in carousels" :key="carousel" class="info_item">
          <strong class="tit_item" v-html="carousel.tit"/>
          <p class="desc_item" v-html="carousel.desc"/>
          <p class="txt_info">* 과일토핑은 계절에 따라 변동 될 수 있습니다. *</p>
        </div>
      </div>
    </div>
    <button class="btn_prev" @click="prev()"><span class="ico_mmn ico_prev">이전</span></button>
    <button class="btn_next" @click="next()"><span class="ico_mmn ico_next">이후</span></button>
  </div>
</template>

<script>
  export default {
    name: 'Carousel2Column',
    el: '.wrap_imgs',
    data() {
      return {
        coord: 0,
        carousels: [
          {
            class: 'menu_croffle',
            src: 'static/img_croffle.png',
            imgTitle: 'static/tit_menu5.png',
            tit: '크로플',
            desc: '프랑스 수입 밀가루와 고급 버터로 만들어 풍미가 가득~!<br>속은 촉촉, 쫀득한 식감이 일품인 크로플 입니다. 달콤한 아이스크림과 함께 상큼한 수제 청귤칩으로 깔끔하게 마무리!'
          },
          {
            class: 'menu_icedutch',
            src: 'static/img_icedutch.png',
            imgTitle: 'static/tit_menu1.png',
            tit: '아이스크림 더치베이비',
            desc: '신선하고 상큼한 계절 과일과<br>달콤한 아이스크림과 함께 즐기는<br>독일식 팬케이크 더치 베이비 입니다.'
          },
          {
            class: 'menu_parfait',
            src: 'static/img_parfait.png',
            imgTitle: 'static/tit_menu2.png',
            tit: '마마파르페',
            desc: '어렸을 때 즐겨먹던 추억의 파르페를 마마미니에서 만나보세요!<br>바삭한 그래놀라가 가득 들어 있어요~'
          },
          {
            class: 'menu_honey',
            src: 'static/img_honey.png',
            imgTitle: 'static/tit_menu3.png',
            tit: '허니브레드',
            desc: '겉은 바삭바삭! 속은 촉촉~<br>기본에 충실하게 달콤한 허니브레드!<br>큼직하게 썰어 상큼한 계절 과일과 함께 휘핑 크림을 가득 찍어 한 입 가득 쏘옥~!'
          },
          {
            class: 'menu_avosala',
            src: 'static/img_avosala.png',
            imgTitle: 'static/tit_menu4.png',
            tit: '아보살라 더치베이비',
            desc: '숲 속의 버터 아보카도와 살라미의<br>환상적인 만남!<br>발사믹 식초, 시저드레싱에 찍어<br>마지막 한 입 까지 맛있게 즐겨보세요!'
          }
        ]
      }
    },
    methods: {
      // todo-heeo. 코드리펙토링
      resetTransition() {},
      moveItem() {},
      resetMovePrev() {
        this.carousels.splice(0, 0, this.carousels[this.carousels.length-1]);
        this.carousels.splice(this.carousels.length -1, 1);
        this.$refs.wrapImgs.style.transition = 'all 0s';
        this.$refs.wrapInfos.style.transition = 'all 0s';
        this.$refs.wrapImgs.style.transform = `translate3d(0, 0, 0)`;
        this.$refs.wrapInfos.style.transform = `translate3d(0, 0, 0)`;
        this.coord = 0;
      },
      resetMoveNext() {
        this.carousels.splice(this.carousels.length, 0, this.carousels[0]);
        this.carousels.splice(0, 1);
        this.$refs.wrapImgs.style.transition = 'all 0s';
        this.$refs.wrapInfos.style.transition = 'all 0s';
        this.$refs.wrapImgs.style.transform = `translate3d(0, 0, 0)`; // transition만 초기화 하고 translate3d(0, 0, 0)로 초기화 안해줘서 안되는거 였음......ㅠ
        this.$refs.wrapInfos.style.transform = `translate3d(0, 0, 0)`;
        this.coord = 0;
      },
      prev() {
        this.coord = this.coord + 500;
        this.$refs.wrapImgs.style.transition = 'all 0.5s ease-in-out';
        this.$refs.wrapInfos.style.transition = 'all 0.5s ease-in-out';
        this.$refs.wrapImgs.style.transform = `translate3d(${this.coord}px, 0, 0)`;
        this.$refs.wrapInfos.style.transform = `translate3d(${this.coord}px, 0, 0)`;
        setTimeout(() =>  {
          this.resetMovePrev();
        }, 500);
      },
      next() {
        this.coord = this.coord - 500;
        this.$refs.wrapImgs.style.transition = 'all 0.5s ease-in-out';
        this.$refs.wrapInfos.style.transition = 'all 0.5s ease-in-out';
        this.$refs.wrapImgs.style.transform = `translate3d(${this.coord}px, 0, 0)`;
        this.$refs.wrapInfos.style.transform = `translate3d(${this.coord}px, 0, 0)`;
        setTimeout(() =>  {
          this.resetMoveNext();
        }, 500);
      }
    }
  }
</script>

<style lang="scss" scoped>
  .cont_carousel { // todo-heeo. 클래스명 중복 확인
    position: relative;
    overflow: hidden;
    margin: 0 auto;
    width: 1000px;
    height: 650px;
    box-sizing: border-box;
    border-radius: 7px;
    box-shadow: 4px 12px 30px 6px rgb(0 0 0 / 9%);
    .wrap_item {
      overflow: hidden;
      float: left;
      width: 50%;
      height: 100%;
    }
    .wrap_imgs, .wrap_infos {
      display: flex;
      width: 100%;
      height: 100%;
      margin-left: -500px;
    }
    .wrap_img {
      position: relative;
      transition: all 0.4s ease-in;
      &:hover {
        transform: scale(1.1);
      }
      .menu_icedutch{
        top: 160px;
        left: 50%;
        margin-left: -175px;
      }
      .menu_parfait {
        top: 170px;
        left: 40px;
      }
      .menu_honey {
        top: 150px;
        left: 50%;
        margin-left: -114px;
      }
      .menu_avosala {
        top: 70px;
        right: 20px;
      }
      .menu_croffle {
        top: 70px;
        left: 40px;
      }
    }
    .tit_img {
      position: absolute;
      vertical-align: top;
      &.active {
        transition: all 0.5s ease-in;
      }
    }
    .img_item, .info_item {
      width: 500px;
      height: 100%;
    }
    .info_item {
      padding: 150px 50px;
      background: $color-white;
      color: $baseFontColor;
      box-sizing: border-box;
      .tit_item {
        display: inline-block;
        margin-bottom: 20px;
        font-size: 35px;
        line-height: 40px;
      }
      .desc_item {
        font-size: 27px;
        line-height: 35px;
      }
      .txt_info {
        margin-top: 10px;
        color: $color-point;
        font-size: 20px;
        line-height: 25px;
      }
    }
    .btn_prev, .btn_next {
      position: absolute;
      z-index: 20;
      top: 50%;
      margin-top: -27px;
    }
    .btn_prev {
      left: 40px;
      margin-left: -27px;
    }
    .btn_next {
      left: 435px;
      margin-right: -27px;
    }
  }
</style>