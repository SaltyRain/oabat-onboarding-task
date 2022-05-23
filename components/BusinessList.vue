<template>
  <div class="business-swiper">
    <div class="business-swiper__outer-wrapper">
      <div class="business-swiper__button-container">
        <v-btn icon>
          <v-icon aria-label="swipe left" role="img" aria-hidden="false">
            {{ icons.mdiChevronLeft }}
          </v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon aria-label="swipe right" role="img" aria-hidden="false">
            {{ icons.mdiChevronRight }}
          </v-icon>
        </v-btn>
      </div>
      <div class="business-swiper__business-list">
        <div class="d-flex">
          <swiper
            :space-between="15"
            :breakpoints="swiperOptions.breakpoints"
            :modules="modules"
            @swiper="onSwiper"
            :navigation="true"
          >
            <swiper-slide v-for="business of businesses" :key="business.id">
              <business-card :business="business" :city="city" />
            </swiper-slide>
          </swiper>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mdiChevronRight, mdiChevronLeft } from '@mdi/js'
import { SwiperCore, Swiper, SwiperSlide } from 'swiper-vue2'
import { Navigation, Pagination, Controller } from 'swiper'
import BusinessCard from './BusinessCard.vue'

// Import Swiper styles
import 'swiper/swiper-bundle.css'
import 'swiper/components/navigation/navigation.min.css'
SwiperCore.use([Navigation, Pagination, Controller])

export default {
  components: {
    BusinessCard,
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Navigation],
    }
  },
  props: {
    businesses: {
      type: Array,
      required: true,
    },
    city: {
      type: String,
      required: true,
    },
  },

  data: () => ({
    icons: {
      mdiChevronLeft,
      mdiChevronRight,
    },
    swiperOptions: {
      breakpoints: {
        100: {
          slidesPerView: 1,
        },
        500: {
          slidesPerView: 2,
        },
        1000: {
          slidesPerView: 4,
        },

        1700: {
          slidesPerView: 5,
        },
      },
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
    },
  }),
}
</script>

<style lang="scss" scoped>
@import '@/assets/_variables';
@import '@/assets/_breakpoints';

.business-swiper {
  &__outer-wrapper {
    position: relative;
  }
  &__button-container {
    position: absolute;
    top: -50px;
    right: -16px;
  }
}
</style>
