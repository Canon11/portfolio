<template>
  <v-app>
    <v-toolbar app dark class="indigo">
      <v-toolbar-title class="headline">
        <span>Muratty's Page</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn flat v-on:click="$vuetify.goTo('#profile', scrollOpt)">
          <v-icon>mdi-face-profile</v-icon>
          <span class="ml-1">Profile</span>
        </v-btn>
        <v-btn flat v-on:click="$vuetify.goTo('#timeline', scrollOpt)">
          <v-icon>mdi-timeline</v-icon>
          <span class="ml-1">TimeLine</span>
        </v-btn>
        <v-btn flat v-on:click="$vuetify.goTo('#blog', scrollOpt)">
          <v-icon>mdi-new-box</v-icon>
          <span class="ml-1">New Blog</span>
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>

    <v-content>
      <Eyecatch id="eyecatch"/>
      <v-divider></v-divider>
      <v-container>
        <Profile id="profile"/>
        <v-divider></v-divider>
        <TimeLine id="timeline"/>
        <v-divider></v-divider>
        <Blog id="blog"/>
      </v-container>
    </v-content>
    <v-layout justify-center>
      <v-btn color="pink" dark fab v-on:click="$vuetify.goTo('#eyecatch', scrollOpt)">
        <v-icon>mdi-arrow-up</v-icon>
      </v-btn>
    </v-layout>
    <Footer/>
  </v-app>
</template>

<script>
import Eyecatch from "./components/Eyecatch";
import TimeLine from "./components/TimeLine";
import Profile from "./components/Profile";
import Blog from "./components/Blog";
import Footer from "./components/Footer";
import "@mdi/font/css/materialdesignicons.css";

export default {
  name: "App",
  components: {
    Eyecatch,
    TimeLine,
    Profile,
    Blog,
    Footer
  },
  data() {
    return {
      scrollOpt: {
        duration: 1500,
        offset: 10,
        easing: "easeInOutCubic"
      }
    };
  }
};
</script>
