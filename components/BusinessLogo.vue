<template>
  <img class="card-logo--absolute" :src="logo" />
</template>

<script>
export default {
  props: {
    logo: {
      type: String,
      required: true,
    },
  },
}
</script>
