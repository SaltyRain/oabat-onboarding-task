<template>
  <div class="py-2">Hello World!</div>
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
          
        }
      }
    }
  }
}
</script>
