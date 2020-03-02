<template>
  <div class="bubble-loading">
    20%
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.bubble-loading {
  position: relative;

  width: 50px;
  height: 50px;
  /* linear-gradient(角度值指明渐变方向，startColor，endColor) */
  background-image: linear-gradient(45deg, rgb(14, 14, 46), rgb(64, 64, 113));

  border-radius: 50%;

  display: flex;
  justify-content: center;
  align-items: center;

  font-size: 17px;
  font-weight: bold;
  color: white;

  box-shadow: 0px 3px 10px 0px rgb(0, 0, 0);
}

.bubble-loading::before,
.bubble-loading::after {
  content: "";

  position: absolute;
  width: 100%;
  height: 100%;

  border-radius: 50%;
  background-color: rgb(51, 149, 230);
  z-index: -1;
}
.bubble-loading::before {
  animation: rotate2 infinite 1.5s linear;
}
.bubble-loading::after {
  animation: rotate2 infinite 1s linear;
}
/* 
* 【注】 transform的数值，放在伪元素中是很奇怪，感觉好像会被覆盖一样
* 所以下面的 translateY(-3px) 虽然从0%-100%都没变化，
* 但是不可以直接在 ::before和::after中 添加 transfrom: translateY(-3px)
* 因为，你添加了，但transfrom数值是直接覆盖的，所以 rotate(0deg)就覆盖掉了 translateY，translateY就没效果了
* */
@keyframes rotate2 {
  0% {
    transform: rotate(0deg) translateY(-3px);
  }
  100% {
    transform: rotate(360deg) translateY(-3px);
  }
}
</style>
