<template>
  <v-card class="contentOverflow">
    <!-- <div class="card-content"> -->
    <v-img
      :lazy-src="business.preview_image"
      height="100%"
      width="100%"
      max-height="200px"
      :src="business.preview_image"
      class="full-width full-height"
    />
    <!-- <v-card class="contentOverflow"> -->
    <div class="card-content px-2 py-2">
      <p class="font-weight-bold">{{ business.title }}</p>
      <p>{{ business.description }}</p>
    </div>
    <!-- </v-card> -->

    <!-- <v-card class="mt-n4">
        {{ business.title }}
      </v-card> -->
    <!-- </div> -->
    <!-- <div class="card-content">
      <img :src="business.preview_image" :alt="business.title" />
      {{ business.title }}
    </div> -->
  </v-card>
</template>

<script>
export default {
  props: {
    business: {
      type: Object,
      required: true,
    },
  },
}
</script>
