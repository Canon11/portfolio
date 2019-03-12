<template>
  <div>
    <v-footer dark height="auto">
      <v-card class="flex" flat tile>
        <v-card-title class="indigo">
          <strong class="subheading">Get connected with us on social networks!</strong>

          <v-spacer></v-spacer>

          <v-tooltip bottom open-delay="50" v-for="(social, i) in socials" :key="i">
            <template v-slot:activator="{ on }">
              <v-btn class="mx-3" dark icon :href="social.link" target="_blank" v-on="on">
                <v-icon size="24px">{{ social.icon }}</v-icon>
              </v-btn>
            </template>
            <span>{{ social.name }}</span>
          </v-tooltip>
        </v-card-title>

        <v-card-actions class="grey darken-3 justify-center">
          &copy;2019 —
          <strong>Canon11</strong>
        </v-card-actions>
      </v-card>
    </v-footer>
  </div>
</template>

<script>
export default {
  data: () => ({
    socials: [
      {
        name: "FaceBook",
        icon: "mdi-facebook-box",
        link: "https://www.facebook.com/kazuma.murata.56"
      },
      {
        name: "Twitter",
        icon: "mdi-twitter",
        link: "https://twitter.com/canon1ky"
      },
      {
        name: "GitHub",
        icon: "mdi-github-circle",
        link: "https://github.com/Canon11"
      },
      {
        name: "HatenaBlog",
        icon: "mdi-blogger",
        link: "https://canon1ky.hatenablog.com/"
      }
    ]
  })
};
</script>
