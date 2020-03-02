<template>
  <div class="teacup-loading">
    50%
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.teacup-loading {
  position: relative;

  width: 45px;
  height: 50px;
  background-color: #fff3da;

  display: flex;
  justify-content: center;

  color: rgb(30, 30, 30);
  font-size: 17px;
  font-weight: bold;

  /* 添加了border，但把最上方的border去掉了，再给左下，右下做圆角状 */
  border-radius: 0 0 15px 15px;
  border: 4px solid black;
  border-top: 0px;

  box-shadow: 0 2px 5px 0px black;

  /* 给其弄z-index成-1，给其伪元素也弄成z=-1，然后 20% 还是 z=0，那么就会有透视效果 */
  z-index: -1;

  /* 隐藏子元素溢出部分,其伪元素久可以不必做border-radius了 */
  overflow: hidden;
}
.teacup-loading::before,
.teacup-loading::after {
  content: "";

  position: absolute;
  bottom: 0px;
  left: 0px;
  width: 180px;
  height: 50%;

  /* 给伪元素设置z值，让其可以透过 20% 的字 */
  z-index: -1;

  clip-path: polygon(
    0% 20%,
    2% 18%,
    3% 16%,
    5% 14%,
    7% 13%,
    8% 11%,
    10% 10%,
    12% 10%,
    13% 10%,
    15% 10%,
    17% 11%,
    18% 13%,
    20% 14%,
    22% 16%,
    23% 18%,
    25% 20%,
    27% 22%,
    28% 24%,
    30% 26%,
    32% 27%,
    33% 29%,
    35% 30%,
    37% 30%,
    38% 30%,
    40% 30%,
    42% 29%,
    43% 27%,
    45% 26%,
    47% 24%,
    48% 22%,
    50% 20%,
    52% 18%,
    53% 16%,
    55% 14%,
    57% 13%,
    58% 11%,
    60% 10%,
    62% 10%,
    63% 10%,
    65% 10%,
    67% 11%,
    68% 13%,
    70% 14%,
    72% 16%,
    73% 18%,
    75% 20%,
    77% 22%,
    78% 24%,
    80% 26%,
    82% 27%,
    83% 29%,
    85% 30%,
    87% 30%,
    88% 30%,
    90% 30%,
    92% 29%,
    93% 27%,
    95% 26%,
    97% 24%,
    98% 22%,
    100% 20%,
    100% 100%,
    0% 100%
  );
}

.teacup-loading::before {
  background-color: rgb(255, 214, 125);
  animation: move1 3s infinite linear;
}
.teacup-loading::after {
  background-color: rgb(255, 174, 0);
  animation: move2 6s infinite linear;
}

@keyframes move1 {
  0% {
    left: 0;
  }
  100% {
    left: -90px;
  }
}
@keyframes move2 {
  0% {
    left: -20px;
  }
  100% {
    left: -110px;
  }
}
</style>
