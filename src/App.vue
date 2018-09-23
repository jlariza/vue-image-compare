<template>
  <div id="app">
    <ImageCompare before="assets/before.jpg" after="assets/after.jpg" full isZoomable isSwitchable isDraggable>
      <i class="fa fa-angle-left" aria-hidden="true" slot="icon-left"></i>
      <i class="fa fa-angle-right" aria-hidden="true" slot="icon-right"></i>
    </ImageCompare>
  </div>
</template>

<script>
import ImageCompare from 'vue-image-compare'

export default {
  name: 'app',
  components: {
    ImageCompare
  }
}
</script>

<style lang="scss">
html,
body,
#app {
  height: 100%;
}
body {
  margin: 0;
}
</style>
