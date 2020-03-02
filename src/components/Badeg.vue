<template>
  <div class="badeg">HI</div>
</template>
<script>
export default {};
</script>
<style>
.badeg {
  position: relative;
  width: 50px;
  height: 50px;

  display: flex; /* flex让HI子元素也变成了浮动了 */
  justify-content: center;
  /* align-items: center; */

  border-radius: 4px;
  filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.5));

  color: white;
  font-weight: bold;
  text-shadow: 1px 1px 3px black;

  overflow: hidden;
  animation: shake infinite 1s ease;
}
.badeg::before,
.badeg::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  background-image: linear-gradient(0deg, red, #ff8484);

  /* display: block; 可以抵挡 父元素的text-align:center攻击，
  * 但这里可以不需要用
  * 因为该父亲是用flex来实现居中的
  */
  /* display: block; */

  border-radius: 4px;

  z-index: -1;
}
.badeg::before {
  /* 以右上角作为扭曲点 扭曲 */
  transform-origin: right top;
  transform: skewY(20deg);
}
.badeg::after {
  transform-origin: left top;
  transform: skewY(-20deg);
}
@keyframes shake {
  0% {
    transform: rotate(5deg);
  }
  4% {
    transform: rotate(-5deg);
  }
  8% {
    transform: rotate(5deg);
  }
  12% {
    transform: rotate(-5deg);
  }
  16% {
    transform: rotate(5deg);
  }
  20% {
    transform: rotate(-5deg);
  }
  24% {
    transform: rotate(5deg);
  }
  28% {
    transform: rotate(-5deg);
  }
}
</style>
