<template>
  <div class="py-1">
    <div v-if="ifClicked">
      <v-chip-group active-class="primary--text" column>
        <v-chip
          v-for="tag of tags"
          :key="tag"
          :value="tag"
          class="card-chip-tag"
        >
          {{ tag }}
        </v-chip>
        <button
          class="weitere-button"
          @click="
            () => {
              ifClicked = false
            }
          "
        >
          <span>{{ `weniger` }}</span>
        </button>
      </v-chip-group>
    </div>
    <div v-else class="tags-wrapper">
      <v-chip class="card-chip-tag">
        {{ truncateTag(tags[0]) }}
      </v-chip>
      <button
        class="weitere-button"
        @click="
          () => {
            ifClicked = true
          }
        "
      >
        <span>{{ `+${tags.length - 1} weitere` }}</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ifClicked: false,
    }
  },
  props: {
    tags: {
      type: Array,
      required: true,
    },
  },
  methods: {
    truncateTag(tag) {
      if (tag.length > 10) {
        return tag.substring(0, 10) + '...'
      }
    },
    collapseTags(tags) {
      if (tags.length > 1) {
        if (tags[0].length > 27) {
          return 0
        }
      }
    },
  },
}
</script>

<style lang="scss" scoped>
@import '@/assets/_variables';
@import '@/assets/_breakpoints';
.tags-wrapper {
  display: flex;
  align-items: center;
}
.weitere-button {
  display: block;
  margin-top: -7px;
  font-size: 14px;
  margin-left: 10px;
  color: $colorGrey2;
}
</style>
