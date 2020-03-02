<template>
  <div class="floating-button"></div>
</template>
<script>
export default {};
</script>
<style scoped>
.floating-button {
  position: relative;

  width: 50px;
  height: 50px;
  background-image: linear-gradient(45deg, rgb(100, 0, 150), rgb(10, 120, 210));

  border-radius: 50%;
  box-shadow: 0px 2px 3px 0px black;
}
.floating-button::before,
.floating-button::after {
  content: "";
  position: absolute;
  left: 16px;
  top: 15px;

  width: 20px;
  height: 5px;

  border-style: solid;
  border-width: 4px 0 0 0;
  border-color: white;

  transition: all 0.3s linear;
}
.floating-button::after {
  /** 
  * box-shadow的属性只能添加到盒模型外面，因此内部的东西是不会添加上的，中间还是白色部分。
  * 而drop-shadow就不一样了，他是把选中的所有的非透明区域都做了阴影效果，就相当于一种真正的投影， 
  */
  filter: drop-shadow(0 8px 0 white);
  top: 23px;
}
.floating-button:hover::before {
  filter: drop-shadow(0 0 0 white);
  transform: rotate(45deg) translate(3px, 8px);
}
.floating-button:hover::after {
  filter: none;
  transform: rotate(-45deg);
}
</style>
