<template>
    <div class="zoom-container">

        <!-- <inner-image-zoom class="original"
          src="https://images.unsplash.com/photo-1542216516-dc8bc35b0c97?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2804&q=80"
          zoomSrc="https://images.unsplash.com/photo-1542216516-dc8bc35b0c97?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2804&q=80"
          zoomType="hover"
          hideHint="true"
        />

        <div class="zoom">

        </div> -->

        <image-magnifier
          :src="image"
          :zoom-src="image"
          width="400"
          height="300"
          zoom-width="400"
          zoom-height="300">
        </image-magnifier>
    </div>
</template>

<script>
// import InnerImageZoom from 'vue-inner-image-zoom';
// import 'vue-inner-image-zoom/lib/vue-inner-image-zoom.css';

// import {ImageMagnifier} from 'vue-image-magnifier';

// export default {
//   name: 'Zoomer',
//   data () {
//     return {
//       image: 'https://unpkg.com/vue-image-magnifier@0.1.1/example/img/DA2D9393-4081-4384-B493-95DA1620C26D.png'
//     }
//   },
//   components: {
//     // 'inner-image-zoom': InnerImageZoom,
//     'image-magnifier': ImageMagnifier
//   },
// };

import ImageMagnifier from './plugins/ImageMagnifier.vue'
  export default {
    components: {
      ImageMagnifier
    },
    data() {
      return {
        image: 'https://unpkg.com/vue-image-magnifier@0.1.1/example/img/DA2D9393-4081-4384-B493-95DA1620C26D.png',
      }
    }
  }
</script>

<style>
.zoom-container {
  text-align: left;
}
.original {
  width: 45%;
  display: inline-block;
}
.zoom{
  width: 40%;
  height: 500px;
  display: inline-block;
  border-width: 10px;
  border-style: dashed;
  border-color: #00ff00;
  
}
</style>