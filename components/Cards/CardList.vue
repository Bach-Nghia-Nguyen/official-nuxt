<template>
  <div class="c_3 mb_3">
    <div class="card">
      <div class="front-card">
        <img :src="picture" :alt="`thumbnail of card ${id}`" />
      </div>

      <div class="back-card">{{ keyword }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
    picture: {
      type: String,
      required: true,
    },
    keyword: {
      type: String,
      required: true,
    },
  },
}
</script>
