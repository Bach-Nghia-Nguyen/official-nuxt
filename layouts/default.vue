<template>
  <div>
    <default-header />
    <Nuxt />
    <default-footer />
  </div>
</template>

<script>
import DefaultHeader from '@/components/Header/DefaultHeader.vue'
import DefaultFooter from '@/components/Footer/DefaultFooter.vue'

export default {
  components: {
    DefaultHeader,
    DefaultFooter,
  },
}
</script>
