<template>
  <v-layout align-center justify-center>
    <v-flex sm12>
      <div class="ityped-block" style="height:100vh">
        <div id="ityped" class="display-3 font-weight-light"></div>
      </div>
    </v-flex>
  </v-layout>
</template>

<style scoped>
.ityped-block {
  background-color: black;
  color: white;
}
</style>


<script>
import { init } from "ityped";

export default {
  data: () => ({
    scrollOpt: {
      duration: 1500,
      offset: 10,
      easing: "easeInOutCubic"
    }
  }),
  mounted: function() {
    init("#ityped", {
      strings: [
        "def sayThanks():",
        "print(\"Hello Muratty's Page! Thank's to visit!!\")",
        'print("This is my profiles.")',
        'print("Please scroll down.")'
      ],
      typeSpeed: 55, // 表示する時のスピード
      backSpeed: 30, // 戻る時のスピード
      startDelay: 300, // スタート時の遅延時間
      backDelay: 500, // 戻る時の遅延時間
      loop: false, // ループの有無
      showCursor: true, // カーソル表示の有無
      cursorChar: "|", // カーソルの形状
      onFinished: function() {
        this.$vuetify.goTo("#profile", this.scrollOpt);
      }
    });
  }
};
</script>
