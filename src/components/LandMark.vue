<template>
  <div class="land-mark"></div>
</template>
<script>
export default {};
</script>
<style scoped>
.land-mark {
  position: relative;
  width: 50px;
  height: 50px;
  background-image: linear-gradient(0deg, red, #ff8484);
  filter: drop-shadow(0px 1px 1px black);
  border-radius: 50%;

  animation: jump infinite 2s ease;
}

.land-mark::before {
  content: "";
  position: absolute;
  left: 20px;
  bottom: -4px;

  background-color: red;
  width: 10px;
  height: 10px;

  transform: rotate(45deg);
}
.land-mark::after {
  content: "";
  position: absolute;
  left: calc(50% - 7.5px);
  top: calc(50% - 7.5px);

  background-color: white;
  width: 15px;
  height: 15px;

  border-radius: 50%;
  box-shadow: 0px 0px 3px black inset;
}
@keyframes jump {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(10px);
  }
  75% {
    transform: translateY(0px);
  }
}
</style>
