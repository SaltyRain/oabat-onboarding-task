<template>
  <v-card class="contentOverflow">
    <business-logo :logo="business.logo" />

    <v-chip :dark="true" class="text-details card-chip-city">{{ city }}</v-chip>
    <v-img
      :src="business.preview_image"
      :lazy-src="business.preview_image"
      height="100%"
      width="100%"
      max-height="200px"
      class="full-width full-height card-background-image"
    />

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
import BusinessLogo from './BusinessLogo.vue'
import BusinessTags from './BusinessTags.vue'
export default {
  components: {
    BusinessLogo,
    BusinessTags,
  },
  props: {
    business: {
      type: Object,
      required: true,
    },
    city: {
      type: String,
      retuired: true,
    },
  },
  methods: {
    shortenDescription(description) {
      return description.substring(0, 150) + '...'
    },
  },
}
</script>
