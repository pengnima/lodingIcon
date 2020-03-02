<template>
  <div class="progress-bar"></div>
</template>
<script>
export default {};
</script>
<style scoped>
.progress-bar {
  position: relative;
  top: 15px;
  width: 60px;
  height: 20px;
  background-color: #eee;

  border-radius: 8px;
  overflow: hidden;
}
.progress-bar::before {
  content: "";
  position: absolute;
  width: 20px;
  height: 100%;
  border-radius: 8px;

  background-image: linear-gradient(0deg, rgb(255, 145, 0), yellow);
  filter: drop-shadow(1px 0px 1px rgba(0, 0, 0, 0.2));

  transition: all 0.3s ease;
}
.progress-bar:hover::before {
  width: 50px;
}
</style>
