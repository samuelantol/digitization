<template>
    <div class="basic-element">
        <!-- <vue-image-zoomer
          regular="https://img-comparison-slider.sneas.io/demo/images/before.webp"
          zoom="https://img-comparison-slider.sneas.io/demo/images/after.webp"
        /> -->

        <inner-image-zoom
          src="https://img-comparison-slider.sneas.io/demo/images/before.webp"
          zoomSrc="https://img-comparison-slider.sneas.io/demo/images/after.webp"
          zoomType="hover"
          hideHint="true"
        />
    </div>
</template>

<script>
// import { VueImageZoomer } from 'vue-image-zoomer'
// import 'vue-image-zoomer/dist/style.css';

import InnerImageZoom from 'vue-inner-image-zoom';
import 'vue-inner-image-zoom/lib/vue-inner-image-zoom.css';

export default {
  name: 'Zoomer',
  components: {
    // VueImageZoomer,
    'inner-image-zoom': InnerImageZoom,
  },
};
</script>

<style>
.basic-element {
  margin: 0 0 0 0;
}
</style>