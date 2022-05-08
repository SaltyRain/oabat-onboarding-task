<template>
  <div class="d-flex">
    <BusinessCard
      v-for="business of businesses"
      :key="business.id"
      :business="business"
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
  },
}
</script>
