<template>
  <div class="play-btn"></div>
</template>
<script>
export default {};
</script>
<style scoped>
.play-btn {
  position: relative;

  width: 50px;
  height: 50px;
  background-image: linear-gradient(45deg, #5298ff, #ff00a8);

  border-radius: 50%;
  box-shadow: 0 2px 3px 0px black;
}

.play-btn::before {
  content: "";
  position: absolute;

  left: 20px;
  top: 18px;

  /**
  * 利用boder做的三角键
  * 首先width,height都为0，只做boder，那么每一个方向上的border都会呈一个三角形
  * 让其余三个方向上的颜色都为透明，只显示一个方向，就变成了三角键
  * border-top-width等，是做微调
  */
  width: 0px;
  height: 0px;
  border: 15px solid transparent;
  border-left-color: white;
  border-top-width: 8px;
  border-bottom-width: 8px;

  /*
  * 做滤镜，drop-shadow给图像设置一个阴影效果。
  * 阴影是合成在图像下面，可以有模糊度的。
  * h-shadow v-shadow blur color
  */
  filter: drop-shadow(0 2px 1px rgba(0, 0, 0, 0.2));

  transition: all 0.3s ease;
}

.play-btn::after {
  content: "";

  position: absolute;
  left: 17px;
  top: 15px;

  width: 5px;
  height: 20px;

  /* 其他边框的宽度如果是0，那么剩下的那个边框就不会呈现 梯形 */
  border-left: 5px solid white;
  border-right: 5px solid white;

  filter: drop-shadow(0 2px 1px rgba(0, 0, 0, 0.2));

  opacity: 0;
  transform: scale(0);
  transition: all 0.3s ease;
}

.play-btn:hover::before {
  opacity: 0;
  transform: scale(0);
}
.play-btn:hover::after {
  opacity: 1;
  transform: scale(1);
}
</style>
