<template>
  <div class="py-1">
    <v-chip-group active-class="primary--text" column>
      <v-chip v-for="tag of tags" :key="tag" :value="tag" class="card-chip-tag">
        {{ tag }}
      </v-chip>
    </v-chip-group>
    {{ tags.length - 1 }}
  </div>
</template>

<script>
export default {
  props: {
    tags: {
      type: Array,
      required: true,
    },
  },
  methods: {
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
