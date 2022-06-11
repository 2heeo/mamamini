<template>
  <div class="cont_location">
    <strong class="tit_location">오시는 길</strong>
    <div class="cont_info">
      <div id="mapMmn" class="map_mmn"></div>
      <div class="wrap_info">
        <dl class="dl_comm">
          <dt><span class="ico_mmn ico_pin">주소</span></dt>
          <dd>제주특별자치도 제주시 조천읍 와선로 238</dd>
        </dl>
        <dl class="dl_comm">
          <dt><span class="ico_mmn ico_tel">전화</span></dt>
          <dd>064-782-0238</dd>
        </dl>
        <dl class="dl_comm">
          <dt><span class="ico_mmn ico_time">영업시간</span></dt>
          <dd>매주 수 ~ 일 (am 11:00 - pm 18:00)</dd>
        </dl>
      </div>
    </div>
  </div>
</template>

<script>
  // const { kakao } = window;
  export default {
    head() {
      return {
        script: [{src: 'https://dapi.kakao.com/v2/maps/sdk.js?autoload=false&appkey=3af2ba1dec4726f0841885b084616f16&libraries=services'}]
      }
    },
    data() {
      return {
        map: null,
      };
    },
    mounted() {
      kakao.maps.load(this.initMap);
    },
    methods: {
      initMap() {
        const container = document.getElementById('mapMmn'); //지도를 담을 영역의 DOM 레퍼런스
        const options = {
          //지도를 생성할 때 필요한 기본 옵션
          center: new kakao.maps.LatLng(126.6982529, 33.4845049), //지도의 중심좌표.
          level: 5, //지도의 레벨(확대, 축소 정도)
        };
        const map = new kakao.maps.Map(container, options); //지도 생성 및 객체 리턴
        this.map = map;

        // 주소-좌표 변환 객체를 생성합니다
        const geocoder = new kakao.maps.services.Geocoder();

        // 주소로 좌표를 검색합니다
        geocoder.addressSearch(
          '제주특별자치도 제주시 와선로 238',
          function (result, status) {
            // 정상적으로 검색이 완료됐으면
            if (status === kakao.maps.services.Status.OK) {
              const coords = new kakao.maps.LatLng(result[0].y, result[0].x);

              // 결과값으로 받은 위치를 마커로 표시합니다
              const marker = new kakao.maps.Marker({
                map: map,
                position: coords,
              });

              // 인포윈도우로 장소에 대한 설명을 표시합니다
              const infowindow = new kakao.maps.InfoWindow({
                content:
                  '<div style="width:150px;text-align:center;padding:6px 0;">마마미니</div>',
              });
              infowindow.open(map, marker);

              // 지도의 중심을 결과값으로 받은 위치로 이동시킵니다
              map.setCenter(coords);
            }
          }
        );
      },
    },
  };
</script>

<style lang="scss" scoped>
  .cont_location {
    padding: 50px 0;
    background: $color-bg;
    box-sizing: border-box;
  }
  .tit_location {
    display: block;
    padding: 50px 0;
    text-align: center;
    color: $color-dark;
    font-size: 40px;
  }
  .cont_info {
    width: 1200px;
    margin: 0 auto;
  }
  .map_mmn {
    width: 100%;
    height: 300px;
  }
  .wrap_info {
    padding: 20px 0;
  }
  .dl_comm {
    display: table-row;
    overflow: hidden;
    width:  auto;
    line-height: 25px;
    dt {
      padding: 10px 0;
      display: table-cell;
    }
    dd {
      display: table-cell;
      padding: 10px 0 0 10px;
    }
  }
</style>
