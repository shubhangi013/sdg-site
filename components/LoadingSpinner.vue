<template functional>
  <div :class="`spinner-wrapper spinner-position-${props.position}`">
    <div class="spinner"></div>
  </div>
</template>

<script>
import { defineComponent } from '@nuxtjs/composition-api'
export default defineComponent({
  name: 'LoadingSpinner',
  props: {
    position: { type: String, default: 'relative' }
  }
})
</script>

<style scoped lang="scss">
* {
  margin: 0;
  padding: 0;
}
@keyframes spinner {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
.spinner-wrapper {
  width: 75px;
  height: 75px;
}
.spinner-position-absolute {
  width: 0;
  height: 0;
  .spinner {
    position: absolute;
    left: calc(50% - 37.5px);
    top: calc(50% - 37.5px);
    transform: translate(-50%, -50%);
  }
}
.spinner {
  opacity: 0.2;
  background: black;
  width: 75px;
  height: 75px;
  border-radius: 50%;
  border: black 4px solid;
  border-left-color: transparent;
  border-right-color: transparent;
  animation: spinner 1.5s infinite;
}
</style>
