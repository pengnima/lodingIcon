<template>
  <div class="circle-loading">
    20%
  </div>
</template>
<script>
export default {};
</script>
<style>
.circle-loading {
  width: 50px;
  height: 50px;
  position: relative;

  /* 让 20% 垂直居中 */
  display: flex;
  justify-content: center; /* 子元素在主轴 中心对齐 */
  align-items: center; /* 子元素在侧轴 中心对齐 */

  /* 边框样式,box-shadow 内外都设置了阴影*/
  border-radius: 50%;
  border: 4px solid rgb(184, 184, 184);
  box-shadow: 0px 0px 2px 1px rgb(184, 184, 184) inset,
    0px 0px 2px 1px rgb(184, 184, 184);

  /* 字体样式 */
  font-size: 17px;
  font-weight: bold;
  color: rgb(175, 19, 170);
}

.circle-loading::before {
  content: "";

  /* 绝对定位，让其根据circle-loading定位，不定位width和height都无法生效 */
  /* 设置position: absolute;后这个元素的display属性计算为block值； */
  position: absolute;

  width: 50px;
  height: 50px;

  /* 让子元素的border为透明，只让其 border-top显示出颜色。不能只添加top的样式，因为这样做样式会变尖 */
  border: 4px solid transparent;
  border-radius: 50%;
  border-top-color: green;

  animation: rotate1 infinite 1s;
}

@keyframes rotate1 {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
