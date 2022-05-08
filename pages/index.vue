<template>
  <div>
    <v-card class="pa-2 mx-2 mx-md-4 mt-4 welcome-card text-center">
      <div class="headline-md">Implement your task here</div>
      <div class="text-body">Contact @Julian if help is needed.</div>
    </v-card>

    <div class="mx-2 mx-md-4 mt-4">
      <h2 class="headline-lg mb-3">
        Einzigartige <strong>Arbeitgeber</strong> aus <strong>Passau</strong>
      </h2>
      <BusinessList :businesses="businesses" />
    </div>
  </div>
</template>

<script>
import BusinessList from '@/components/BusinessList'
export default {
  components: {
    BusinessList,
  },
  computed: {
    businesses() {
      return this.$store.state.default.businesses
    },
  },
  // data() {
  //   return {
  //     businesses: [
  //       { id: 1, logo: '', title: 'sosi hui' },
  //       { id: 2, logo: '', title: 'slava urkaini' },
  //       { id: 3, logo: '', title: 'ZA DONBASS NAHUI' },
  //     ],
  //   }
  // },
}
</script>

<style lang="scss" scoped>
@import '@/assets/_variables';
@import '@/assets/_breakpoints';

.welcome-card {
  background: $colorPrimaryWhite;
  height: 300px;
  width: 300px;
  @include md-and-up {
    width: 600px;
  }
}
</style>
