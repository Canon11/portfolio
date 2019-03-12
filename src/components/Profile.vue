<template>
  <div class="my-5">
    <div class="display-2 font-weight-regular font-italic text-xs-center">Kazuma Murata</div>
    <div class="title font-weight-light font-italic text-xs-center">Back end engineer</div>
    <v-layout justify-center class="mt-4" v-if="categoryShowNum == 0">
      <v-flex sm5>
        <img width="100%" :src="require('../assets/muratty_icon.png')">
      </v-flex>
      <v-flex sm7 class="px-3">
        <v-card class="px-2 py-2">
          <div>
            <div class="display-1 font-weight-regular font-italic">About</div>
          </div>
          <div class="mt-4">
            <p>24歳、山梨県出身。</p>
            <p>筑波大学で4年間、コンピュータサイエンスを学び、ヒューマンインターフェース分野の研究を行う。2017年3月に学部を卒業し、4月に新卒でWeb系ベンチャー企業に入社。ソーシャルゲームのバックエンドエンジニアとして2本の新規ゲームリリースを経験。インフラ構築・運用から、規格との連携、新規イベント開発、新規機能開発までバックエンドの幅広い分野を担当。</p>
            <p>2018年5月に退職をし、学生時代から共にサービスを開発していた先輩と3人で起業。受託開発や自社システム開発などを行いつつも新規事業に向けて格闘(現在進行形)。</p>
            <p>また、その傍らでプログラミングの講師・メンターとしても活動中。</p>
            <p>趣味はダンス・ピアノ・バイオハザード。</p>
          </div>
        </v-card>
      </v-flex>
    </v-layout>

    <v-layout justify-center class="mt-4" v-if="categoryShowNum == 1">
      <v-flex>
        <v-card class="px-2 py-2">
          <div class="display-1 font-weight-regular text-xs-center font-italic">Skills</div>
          <div class="text-xs-center">
            <div v-for="(skill, index) in skills" :key="index">
              <div class="title font-weight-light font-italic mt-3 mb-1">{{ skill.title }}</div>
              <v-chip
                outline
                color="primary"
                v-for="(content, index) in skill.contents"
                :key="index"
              >{{ content }}</v-chip>
            </div>
          </div>
        </v-card>
      </v-flex>
    </v-layout>

    <v-layout row justify-space-around class="mt-4" v-if="categoryShowNum == 2">
      <v-flex sm3 v-for="(created, j) in createds" :key="j">
        <v-card>
          <v-img :src="created.image" height="200px"></v-img>

          <v-card-title primary-title>
            <div>
              <div class="headline">{{ created.title }}</div>
              <span class="grey--text">{{ created.subtitle }}</span>
            </div>
          </v-card-title>

          <v-card-actions>
            <v-btn flat color="purple" :href="created.source" target="_blank">Explore</v-btn>
            <v-spacer></v-spacer>
            <v-btn icon @click="created.show = !created.show">
              <v-icon>{{ created.show ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
            </v-btn>
          </v-card-actions>

          <v-slide-y-transition>
            <v-card-text v-show="created.show">{{ created.description }}</v-card-text>
          </v-slide-y-transition>
        </v-card>
      </v-flex>
    </v-layout>

    <div class="text-xs-center">
      <v-menu offset-y>
        <v-btn slot="activator" color="primary" dark>Change</v-btn>
        <v-list>
          <v-list-tile v-for="(title, index) in items" :key="index" @click="selectCategory(index)">
            <v-list-tile-title>{{ title }}</v-list-tile-title>
          </v-list-tile>
        </v-list>
      </v-menu>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    categoryShowNum: 0,
    items: ["About", "Skills", "Created"],
    skills: [
      {
        title: "Language",
        contents: ["Python", "PHP", "JavaScript", "Golang", "GoogleAppsScript"]
      },
      {
        title: "Framework",
        contents: ["Django", "ZendFramework", "Laravel", "Vue.js", "React.js"]
      },
      {
        title: "Cloud",
        contents: [
          "ELB",
          "ElasticBeanstalk",
          "CloudWatch",
          "Aurora",
          "CloudFront",
          "GAE",
          "GKE",
          "CloudSQL"
        ]
      },
      {
        title: "MicroService",
        contents: [
          "Docker",
          "Kubernetes",
          "CircleCI",
          "UnitTest",
          "Selenium",
          "gRPC"
        ]
      },
      {
        title: "Other",
        contents: [
          "MySQL",
          "Gulp",
          "AWS Solutions Architect Associate",
          "WordPress"
        ]
      }
    ],
    createds: [
      {
        title: "YAlert",
        subtitle: "Chrome Extention",
        description: "Youtubeの見過ぎを防ぐChrome拡張機能",
        image: require("../assets/yalert.png"),
        source: "https://github.com/Canon11/dj-cref",
        show: false
      },
      {
        title: "dj-cref",
        subtitle: "Python Package",
        description: "Djangoの汎用ビューを自動生成するPythonパッケージ",
        image: require("../assets/djcref.png"),
        source: "https://github.com/Canon11/YAlert",
        show: false
      },
      {
        title: "TweetAutoFollow",
        subtitle: "Development Tool",
        description: "コマンドラインで動くツイッター自動フォローシステム",
        image: require("../assets/tweetfollow.png"),
        source: "https://github.com/Canon11/TweetAutoFollow",
        show: false
      }
    ]
  }),
  methods: {
    selectCategory: function(i) {
      this.categoryShowNum = i;
    }
  }
};
</script>
