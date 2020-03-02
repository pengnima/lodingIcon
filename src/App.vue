<template>
  <!-- 学习自av71126754，Up: lizzzled -->
  <div id="app">
    <div>
      <circle-loading></circle-loading>
    </div>
    <div>
      <bubble-loading></bubble-loading>
    </div>
    <div>
      <teacup-loading></teacup-loading>
    </div>
    <div>
      <play-button></play-button>
    </div>
    <div>
      <floating-button></floating-button>
    </div>
    <div>
      <progress-bar></progress-bar>
    </div>
    <div>
      <badeg></badeg>
    </div>
    <div>
      <land-mark></land-mark>
    </div>
    <div><heart></heart></div>
  </div>
</template>

<script>
import CircleLoading from "./components/CircleLoading.vue";
import BubbleLoading from "./components/BubbleLoading.vue";
import TeacupLoading from "./components/TeacupLoading.vue";
import PlayButton from "./components/PlayButton.vue";
import FloatingButton from "./components/FloatingButton.vue";
import ProgressBar from "./components/ProgressBar.vue";
import Badeg from "./components/Badeg.vue";
import LandMark from "./components/LandMark.vue";
import Heart from "./components/Heart.vue";

export default {
  name: "App",
  components: {
    CircleLoading,
    BubbleLoading,
    TeacupLoading,
    PlayButton,
    FloatingButton,
    ProgressBar,
    Badeg,
    LandMark,
    Heart
  }
};
</script>

<style>
#app {
  display: flex;
  width: 520px;
  flex-wrap: wrap;
}
#app > div {
  margin-left: 30px;
  margin-top: 30px;
}
</style>
