<template>
  <carousel-3d
    autoplay
    autoplay-hover-pause
    perspective="35"
    height="350"
    width="500"
    :inverse-scaling="1500"
    :space="width"
  >
    <template v-for="n in 5">
      <slide :index="n - 1" :key="n" @click="onClickEvent()" @mouseover="onMounseOverEvent()">
        {{ `Slide ${n} Content` }}
      </slide>
    </template>
  </carousel-3d>
</template>

<script>
import { Carousel3d, Slide } from 'vue-carousel-3d';

export default {
  components: {
    Carousel3d,
    Slide,
  },
  computed: {
    width() {
      return window.innerWidth;
    },
  },
  methods: {
    onClickEvent() {
      this.$emit('on-click-event')
    },
    onMounseOverEvent() {
      this.$emit('on-mouse-over-event')
    },
  },
};
</script>

<style lang="scss" scoped>
.carousel-3d-container {
  margin: 0;
  position: absolute;
  top: 50%;
  left: 0%;
  transform: translate(0, -50%);
}
</style>
