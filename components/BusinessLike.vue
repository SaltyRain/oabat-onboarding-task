<template>
  <v-btn
    fab
    class="business-like"
    @click="$store.commit('default/handleLikeClick', id)"
  >
    <v-icon>
      {{ is_liked ? icons.mdiCardsHeart : icons.mdiCardsHeartOutline }}
    </v-icon>
  </v-btn>
</template>

<script>
import { mdiCardsHeartOutline, mdiCardsHeart } from '@mdi/js'

export default {
  props: {
    is_liked: {
      type: Boolean,
      required: true,
    },
    id: {
      type: Number,
      required: true,
    },
  },
  data: () => ({
    icons: {
      mdiCardsHeartOutline,
      mdiCardsHeart,
    },
  }),
}
</script>

<style scoped>
.business-like {
  position: absolute;
  z-index: 1;
  right: 10px;
  top: 140px;
  height: 45px !important;
  width: 45px !important;
}
</style>
