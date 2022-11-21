<template>
    <div>
        <div style="width:400px">
            <zoom-on-hover img-normal="https://img-comparison-slider.sneas.io/demo/images/before.webp"></zoom-on-hover>
        </div>
    </div>
</template>

<script>
import * as zoomOnHover from "./plugins/zoomOnHover.js";
import "./plugins/zoomOnHover.css"

export default {
  name: 'Zoomer',
  components: {
    zoomOnHover: zoomOnHover,
  },
};
</script>

<style>

</style>