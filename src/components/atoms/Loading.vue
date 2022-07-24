<template>
  <div class="loading-wrap">
    <div class="loading-content">
      <div class="loading-cover">
        <p>Loading...</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.loading-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background: #0c1022;
  .loading-content {
    position: relative;
    width: 60vw;
    height: 50vh;
    background: rgba(0, 0, 0, 0.75);
    border-radius: 28px;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    &::before {
      content: '';
      position: absolute;
      width: 100vw;
      height: 100vw;
      background-image: conic-gradient(transparent, transparent, transparent, #00ccff);
      animation: animate 4s linear infinite;
    }
    &::after {
      content: '';
      position: absolute;
      width: 100vw;
      height: 100vw;
      background-image: conic-gradient(transparent, transparent, transparent, #d400f4);
      animation: animate 4s linear infinite;
      animation-delay: -2s;
    }
    .loading-cover {
      position: absolute;
      inset: 5px;
      border-radius: 24px;
      background: #0c1022;
      z-index: 1;
      p {
        color: #fff;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        font-size: 48px;
        animation: text_anime_on 2s linear infinite;
      }
    }
  }
}

@keyframes animate {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
@keyframes text_anime_on {
	0% {
    opacity:0;
  }
	100% {
    opacity:1;
  }
}
</style>
