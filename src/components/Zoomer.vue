<template>
    <h2>Sken starých fotografií vo vysokom rozlíšení</h2>
    <div class="zoom-container">
        <image-magnifier
          :src="image"
          :zoom-src="image"
          width="600"
          height="800"
          zoom-width="600"
          zoom-height="800">
        </image-magnifier>
    </div>
</template>

<script>
import ImageMagnifier from './plugins/ImageMagnifier.vue'
  export default {
    components: {
      ImageMagnifier
    },
    data() {
      return {
        image: 'https://images.unsplash.com/photo-1542216516-dc8bc35b0c97?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2804&q=80',
      }
    }
  }
</script>

<style>
.zoom-container {
  text-align: left;
}
/* @media (max-width: 1024px) {
  .zoom-container {
    display: none;
  }
} */
</style>