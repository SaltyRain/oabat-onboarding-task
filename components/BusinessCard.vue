<template>
  <v-card class="contentOverflow">
    <business-like :is_liked="business.is_liked" :id="business.id" />

    <v-chip :dark="true" class="text-details card-chip-city">{{ city }}</v-chip>
    <v-img
      :src="business.preview_image"
      :lazy-src="business.preview_image"
      height="100%"
      width="100%"
      max-height="200px"
      class="full-width full-height card-background-image"
    />
    <business-logo :logo="business.logo" />
    <div class="card-content px-2 py-2">
      <div class="card-info">
        <p class="headline-xs font-weight-bold">{{ business.title }}</p>
        <business-tags :tags="business.tags" />
        <p class="text-body">
          {{ shortenDescription(business.description) }}
        </p>
      </div>
    </div>
  </v-card>
</template>

<script>
import BusinessLogo from '@/components/BusinessLogo'
import BusinessTags from '@/components/BusinessTags'
import BusinessLike from './BusinessLike.vue'
export default {
  components: {
    BusinessLogo,
    BusinessTags,
    BusinessLike,
  },
  props: {
    business: {
      type: Object,
      required: true,
    },
    city: {
      type: String,
      retuired: true,
      default: 'Passau',
    },
  },
  methods: {
    shortenDescription(description) {
      return description.substring(0, 150) + '...'
    },
  },
}
</script>
