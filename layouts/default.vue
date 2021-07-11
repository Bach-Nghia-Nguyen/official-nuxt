<template>
  <div>
    <default-header />
    <Nuxt />
  </div>
</template>

<script>
import DefaultHeader from '@/components/Header/DefaultHeader.vue'

export default {
  components: {
    DefaultHeader,
  },
}
</script>
