<template>
  <div class="d-flex justify-space-between">
    <BusinessCard
      v-for="business of businesses"
      :key="business.id"
      :business="business"
      :city="city"
      class="mr-2"
    />
  </div>
</template>

<script>
import BusinessCard from '@/components/BusinessCard'
export default {
  components: {
    BusinessCard,
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
}
</script>
