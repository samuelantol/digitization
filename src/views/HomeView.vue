<template>
  <main>
    <Zoomer />
    <p>{{text}}</p>
    <Slider />
    <Rotator />
  </main>
</template>

<script setup>
import Zoomer from '../components/Zoomer.vue'
import Slider from '../components/Slider.vue'
import Rotator from '../components/Rotator.vue'

import { ref } from 'vue'

const text = ref("Hello");
</script>
