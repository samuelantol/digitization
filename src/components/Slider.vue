<template>
    <h2>Sken grafík s pečaťami vo vysokom rozlíšení</h2>
    <div>
        <ImgComparisonSlider>
            <!-- eslint-disable -->
            <img
                slot="first"
                style="width: 100%"
                src="https://img-comparison-slider.sneas.io/demo/images/before.webp"
            />
            <img
                slot="second"
                style="width: 100%"
                src="https://img-comparison-slider.sneas.io/demo/images/after.webp"
            />
            <svg slot="handle" width="114" height="36" viewBox="0 0 114 36" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M92.3553 4.00006L106.497 18.1422L92.3553 32.2843" stroke="#00FF00" stroke-width="10" />
                <path d="M21.3553 32.2843L7.2132 18.1422L21.3553 4.00003" stroke="#00FF00" stroke-width="10" />
            </svg>
            
            <!-- eslint-enable -->
        </ImgComparisonSlider>
    </div>
</template>

<script>
import { ImgComparisonSlider } from '@img-comparison-slider/vue';

export default {
  name: 'Slider',
  components: {
    ImgComparisonSlider,
  },
};
</script>

<style type="text/css">
  img-comparison-slider {
    --divider-width: 10px;
    --divider-color: #00ff00;

    --default-handle-color: #00ff00;
    --default-handle-width: clamp(40px, 10vw, 200px);
    --default-handle-opacity: 1;

    outline: none;
  }
  .divider{
    border-left-style: dashed !important;
  }
  .divider:after{
    border-left-style: dashed !important;
  }
</style>