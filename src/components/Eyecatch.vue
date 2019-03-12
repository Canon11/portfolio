<template>
  <v-layout align-center justify-center>
    <v-flex sm3>
      <div class="left-block pt-2">
        <ul>
          <!-- 1階層目のフォルダをループ -->
          <li v-for="(rootFolder, i) in rootFolders" :key="i">
            <v-icon v-if="rootFolder.folders.length > 0" color="orange">{{ rootFolder.icon }}</v-icon>
            <v-icon v-else dark>{{ rootFolder.icon }}</v-icon>
            <span
              class="ml-1"
              :class="{ main_filename: rootFolder.folders.length > 0}"
            >{{ rootFolder.name }}</span>

            <ul v-if="rootFolder.folders.length > 0">
              <!-- 2階層目のフォルダをループ。この層のみ、別ページへのリンクが存在する。 -->
              <li v-for="(folder, j) in rootFolder.folders" :key="j">
                <v-tooltip bottom open-delay="50">
                  <template v-slot:activator="{ on }">
                    <a :href="folder.source" target="_blank" v-on="on">
                      <v-icon v-if="folder.files.length > 0" color="orange">{{ folder.icon }}</v-icon>
                      <v-icon v-else dark>{{ folder.icon }}</v-icon>
                      <span
                        class="ml-1"
                        :class="{ main_filename: folder.files.length > 0 }"
                      >{{ folder.name }}</span>
                    </a>
                  </template>
                  <span>Open Link</span>
                </v-tooltip>

                <ul v-if="folder.files.length > 0">
                  <!-- 3階層目のフォルダをループ -->
                  <li v-for="(file, k) in folder.files" :key="k">
                    <v-icon v-if="file.is_main" color="orange">{{ file.icon }}</v-icon>
                    <v-icon v-else dark>{{ file.icon }}</v-icon>
                    <span class="ml-1" :class="{ main_filename: file.is_main }">{{ file.name }}</span>
                  </li>
                </ul>
              </li>
            </ul>
          </li>
        </ul>
      </div>
    </v-flex>
    <v-flex sm9>
      <div class="right-block pl-3">
        <div id="ityped" class="display-3 font-weight-light"></div>
      </div>
    </v-flex>
  </v-layout>
</template>

<style scoped>
.left-block {
  background-color: gray;
  color: white;
  height: 100vh;
}
.left-block ul {
  list-style: none;
}
.left-block a {
  text-decoration: none;
  color: inherit;
  display: inline-block;
}
.left-block a:hover {
  -webkit-animation: zoom 0.3s;
  animation: zoom 0.3s;
}
@-webkit-keyframes zoom {
  50% {
    -webkit-transform: scale(1.1);
  }
}
@keyframes zoom {
  50% {
    transform: scale(1.1);
  }
}
.main_filename {
  color: orange;
}
.right-block {
  background-color: black;
  color: white;
  height: 100vh;
}
#ityped {
  white-space: pre;
}
</style>

<script>
import { init } from "ityped";
import Vue from "vue";
import "@mdi/font/css/materialdesignicons.css";

export default {
  data: () => ({
    // 左ブロックに表示するファイル一覧
    rootFolders: [
      {
        name: "Projects",
        icon: "mdi-folder",
        folders: [
          {
            name: "Portfolio",
            icon: "mdi-folder-star",
            source: "https://github.com/Canon11/portfolio",
            files: [
              {
                name: "welcome.py",
                icon: "mdi-language-python",
                is_main: true // is_mainをtrueにしておくと、ファイル名がオレンジでハイライトされる
              },
              {
                name: "profile.py",
                icon: "mdi-language-python",
                is_main: false
              },
              {
                name: "timeline.py",
                icon: "mdi-language-python",
                is_main: false
              },
              {
                name: "new_blogs.py",
                icon: "mdi-language-python",
                is_main: false
              },
              {
                name: "README.md",
                icon: "mdi-information-outline",
                is_main: false
              },
              {
                name: ".gitignore",
                icon: "mdi-git",
                is_main: false
              }
            ]
          },
          {
            name: "dj-cref",
            icon: "mdi-folder-star",
            source: "https://github.com/Canon11/dj-cref",
            files: []
          },
          {
            name: "TweetAutoFollow",
            icon: "mdi-folder-star",
            source: "https://github.com/Canon11/TweetAutoFollow",
            files: []
          },
          {
            name: "YAlert",
            icon: "mdi-folder-star",
            source: "https://github.com/Canon11/YAlert",
            files: []
          }
        ]
      },
      {
        name: "Documents",
        icon: "mdi-folder",
        folders: []
      },
      {
        name: "Downloads",
        icon: "mdi-folder",
        folders: []
      }
    ]
  }),
  mounted: function() {
    // 右ブロックのタイピング設定
    init("#ityped", {
      strings: [
        "$ emacs welcome.py",
        "def main():\n" +
          '\tprint("Hello Muratty\'s Page!")\n' +
          '\tprint("This is my portfolio.")\n' +
          '\tprint("Please scroll down.")\n\n' +
          'if __name__ == "__main__":\n' +
          "\tmain()",
        "$ python welcome.py"
      ],
      typeSpeed: 35, // 表示する時のスピード
      backSpeed: 0.5, // 戻る時のスピード
      startDelay: 500, // スタート時の遅延時間
      backDelay: 600, // 戻る時の遅延時間
      loop: false, // ループの有無
      onFinished: function() {
        // ある程度スクロールしているときは、強制的にスクロールさせない
        if (window.pageYOffset > 300) {
          return;
        }
        // アニメーションが終わったら、profile部分にスクロールさせる
        Vue.prototype.$vuetify.goTo("#profile", {
          duration: 1500,
          offset: 10,
          easing: "easeInOutCubic"
        });
      }
    });
  }
};
</script>
