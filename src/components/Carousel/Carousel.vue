<template>
  <div class="swiperbox">
    <Swiper :slidesPerView="1" :spaceBetween="30" :loop="true" :centeredSlides="true" :pagination="{
      clickable: true
    }" :autoplay="{
  delay: 5522200,
  disableOnInteraction: false
}" :navigation="true" :modules="modules" @slideChange="onSlideChange" class="mySwiper">
      <swiper-slide v-for="item in props.list" :key="item?.id">
        <img alt="轮播图" :src="item.imgUrl" />
      </swiper-slide>
    </Swiper>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay, Navigation, Pagination, A11y } from 'swiper'
import 'swiper/css'
import 'swiper/css/navigation'
import 'swiper/css/pagination'

const emit = defineEmits(['response'])
const currentSwipperIndex = ref(0)
const onSlideChange = (swiper: any) => {
  currentSwipperIndex.value = swiper.realIndex
  emit('response', swiper.realIndex)
}

interface CarouselItem {
  id: number
  imgUrl: string
}

const modules = ref([Autoplay, Pagination, Navigation, A11y])
const props = defineProps<{
  list?: CarouselItem[]
}>()

</script>

