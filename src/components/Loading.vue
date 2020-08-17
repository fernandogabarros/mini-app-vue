<template>
  <div class="loading">
    <span></span>
    <span></span>
    <span></span>
    <span></span>
  </div>
</template>

<script>
export default {
  name: 'loading'
}
</script>

<style scoped>
.loading span {
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 10px;
  background: #4B8;
  margin: 0 4px;
  animation: dots .4s infinite alternate cubic-bezier(.4,.1,1,.4);
}
span:nth-child(1) {
  animation-delay: .1s;
}
span:nth-child(2) {
  animation-delay: .2s;
}
span:nth-child(3) {
  animation-delay: .4s;
}
span:nth-child(4) {
  animation-delay: .6s;
}
@keyframes dots {
  from {
    transform: translate3d(0,0,0);
  }
  to {
    transform: translate3d(0, 30px, 0)
  }
}
</style>