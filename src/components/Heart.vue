<template>
  <div class="heart"></div>
</template>
<script>
export default {};
</script>
<style scoped>
.heart {
  display: flex;
  width: 50px;
  height: 50px;
  filter: drop-shadow(0 1px 1px #973340);

  animation: breath 0.8s infinite ease-in;
}
.heart::before,
.heart::after {
  content: "";
  flex: 1;
  height: 40px;
  border-radius: 15px 15px 2px 2px;
}
.heart::before {
  transform: rotate(-45deg) translate(2px, 8px);
  background-image: linear-gradient(90deg, red, #ff6666);
}
.heart::after {
  transform: rotate(45deg) translate(-2px, 8px);
  background-image: linear-gradient(0deg, red, #ff6666);
}
@keyframes breath {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
  75% {
    transform: scale(1);
  }
}
</style>
<!-- 
<style scoped>
.heart {
  position: relative;

  width: 50px;
  height: 50px;
  transform: rotate(-45deg);
  border-radius: 2px;
  overflow: hidden;
}
.heart::before,
.heart::after {
  content: "";
  position: absolute;
  top: 13px;

  width: 25px;
  height: 50px;
  background-color: red;

  border-radius: 15px 15px 0 0;
  transform: none;
}
.heart::before {
  transform: rotate(90deg);
}
.heart::after {
  transform: rotate(0deg);
}
</style>
-->
