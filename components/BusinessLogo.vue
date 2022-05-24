<template>
  <img class="card-logo--absolute" :src="logo || placeholder" />
</template>

<script>
import placeholderImage from '@/static/logo-placeholder-image.png'
export default {
  data() {
    return {
      placeholder: placeholderImage,
    }
  },
  props: {
    logo: {
      type: String,
      required: true,
    },
  },
}
</script>
