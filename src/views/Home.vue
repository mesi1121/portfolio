<template>
  <div class="home">
    <transition-group name="init">
      <loading key="loading" v-if="isLoading" />
      <template v-else>
        <p key="text" v-text="'WELLCOME TO MY WORLD!!!'"></p>
        <carousel key="carousel" />
      </template>
    </transition-group>
  </div>
</template>

<script>
import Loading from '@/components/atoms/Loading.vue'
import Carousel from '@/components/atoms/Carousel.vue';

export default {
  name: 'Home',
  components: {
    Loading,
    Carousel,
  },
  data() {
    return {
      isLoading: true,
    }
  },
  mounted() {
    setTimeout(() => {
      this.isLoading = false
    }, 5000)
  },
};
</script>

<style lang="scss" scoped>
.home {
  height: 100vh;
  position: relative;
  p {
    color: #333;
    font-size: 48px;
    text-align: center;
    margin-top: 0.5em;
  }
}
</style>

<style lang="scss" scoped>
.init-enter-active,
.init-leave-active {
  transition: opacity 1s;
}
.init-enter,
.init-leave-to {
  opacity: 0;
}
</style>
