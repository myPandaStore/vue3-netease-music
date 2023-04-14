<script setup lang="ts">
import { ref, computed, nextTick } from 'vue'
import Carousel from '@/components/Carousel/Carousel.vue'
import img1 from '@/assets/Home/c1.jpg'
import img2 from '@/assets/Home/c-2.jpg'
import img3 from '@/assets/Home/c-3.jpg'
import img4 from '@/assets/Home/c-4.jpg'
import img5 from '@/assets/Home/c-5.jpg'
import img6 from '@/assets/Home/c-6.jpg'
import img7 from '@/assets/Home/c-7.jpg'
import img8 from '@/assets/Home/c-8.jpg'

// 初始化轮播图数据 mock
const CarouselList = ref([
    { id: 1, maskId: 1, imgUrl: img1 },
    { id: 2, maskId: 2, imgUrl: img2 },
    { id: 3, maskId: 3, imgUrl: img3 },
    { id: 4, maskId: 4, imgUrl: img4 },
    { id: 5, maskId: 5, imgUrl: img5 },
    { id: 6, maskId: 6, imgUrl: img6 },
    { id: 6, maskId: 7, imgUrl: img7 },
    { id: 8, maskId: 8, imgUrl: img8 }
])

// 确定 nav 导航栏激活态
const activeNumber = ref(0)

// 当前被展示的轮播图的 index
const currentSlideIndex = ref(0)

// 动态蒙层
const dynamicMask = computed(() => {
    // 根据不同轮播图获取不同的蒙层
    let result
    switch (currentSlideIndex.value) {
        case 0:
            result = "http://p1.music.126.net/NmwcKGRfpHhsb5MNRgsL7A==/109951168540550064.jpg?imageView&blur=40x20"
            break;
        case 1:
            result = "http://p1.music.126.net/hRCZFrT6h2nlw5UHYh0W-g==/109951168540705984.jpg?imageView&blur=40x20"
            break;
        case 2:
            result = "http://p1.music.126.net/SWAGIM0GecRl6sahhdRPxA==/109951168540605488.jpg?imageView&blur=40x20"
            break
        case 3:
            result = "http://p1.music.126.net/ZwJsbKGM4-3wPXcVHLRtSg==/109951168540587598.jpg?imageView&blur=40x20"
            break;
        case 4:
            result = "http://p1.music.126.net/6_ZJVJ2ZHuyW_TuGARXpiA==/109951168541199454.jpg?imageView&blur=40x20";
            break;
        case 5:
            result = "http://p1.music.126.net/h4ZVSYt_cMOr7O5QrWuUnw==/109951168540605107.jpg?imageView&blur=40x20";
            break;
        case 6:
            result = "http://p1.music.126.net/jnn9GbOjIrAgayobtE7viQ==/109951168540908283.jpg?imageView&blur=40x20";
            break;
        case 7:
            result = "http://p1.music.126.net/jnn9GbOjIrAgayobtE7viQ==/109951168540908283.jpg?imageView&blur=40x20"
    }
    return result
})


</script>
<template lang="">
    <p>{{currentSlideIndex}}</p>
  <div class="home">
    <div class="wrap">
      <div class="container">
        <div class="home_nav">
          <div
            :class="activeNumber === 0 ? 'home_nav_item active' : 'home_nav_item'"
            @click="activeNumber = 0"
          >
            推荐
          </div>
          <div
            :class="activeNumber === 1 ? 'home_nav_item active' : 'home_nav_item'"
            @click="activeNumber = 1"
          >
            排行榜
          </div>
          <div
            :class="activeNumber === 2 ? 'home_nav_item active' : 'home_nav_item'"
            @click="activeNumber = 2"
          >
            歌单
          </div>
          <div
            :class="activeNumber === 3 ? 'home_nav_item active' : 'home_nav_item'"
            @click="activeNumber = 3"
          >
            主播电台
          </div>
          <div
            :class="activeNumber === 4 ? 'home_nav_item active' : 'home_nav_item'"
            @click="activeNumber = 4"
          >
            歌手
          </div>
          <div
            :class="activeNumber === 5 ? 'home_nav_item active' : 'home_nav_item'"
            @click="activeNumber = 5"
          >
            新碟上架
          </div>
        </div>
      </div>
    </div>
    <div class="mask" :style="{ 'background-image': 'url(' + dynamicMask + ')' }">
      <div class="home_carousel">
        <Carousel :list="CarouselList" @response="index => currentSlideIndex = index"/>
      </div>
    </div>

    <div class="home_main"></div>
  </div>
</template>

<style lang="less">
.home {
    .wrap {
        background: #c20c0c;

        .container {
            align-items: center;
            width: 1100px;
            margin: 0 auto;
        }
    }

    &_nav {
        display: flex;
        padding-left: 180px;

        &_item {
            display: inline-block;
            height: 20px;
            line-height: 20px;
            color: white;
            padding: 0 13px;
            margin: 7px 17px 7px;

            &:hover {
                cursor: pointer;
            }
        }

        .active {
            border-radius: 20px;
            background: #9b0909;
        }
    }

    .mask {
        // 后面更改为响应式的蒙层
        background-position: center center;
        background-size: 6000px;
    }

    &_carousel {
        width: 982px;
        height: 285px;
        overflow: hidden;
        margin: 0 auto;

        .swiperbox {
            width: 730px;
        }

        .swiper-button-prev {
            color: white;
        }

        .swiper-slide {
            img {
                display: block;
                width: 730px;
                background-size: 6000px;
                // -webkit-backface-visibility: hidden;
            }
        }
    }
}
</style>
