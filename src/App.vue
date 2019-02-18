<template>
<v-app>
    <v-toolbar app dark class="indigo">
        <v-toolbar-title class="headline">
            <span>Canon's Page</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items>
            <v-btn flat v-on:click="$vuetify.goTo('#timeline', scrollOpt)">
                <v-icon>mdi-timeline</v-icon>TimeLine
            </v-btn>
            <v-btn flat v-on:click="$vuetify.goTo('#profile', scrollOpt)">
                <v-icon>mdi-face-profile</v-icon>Profile
            </v-btn>
            <v-btn flat v-on:click="$vuetify.goTo('#blog', scrollOpt)">
                <v-icon>mdi-new-box</v-icon>New Blog
            </v-btn>
        </v-toolbar-items>
    </v-toolbar>

    <v-content>
        <div id="top"></div>
        <PhotoGallery />
        <TimeLine id="timeline" />
        <Profile id="profile" />
        <Blog id="blog" />
    </v-content>
    <v-layout justify-center>
        <v-btn color="pink" dark fab v-on:click="$vuetify.goTo('#top', scrollOpt)">
            <v-icon>mdi-arrow-up</v-icon>
        </v-btn>
    </v-layout>
    <Footer />
</v-app>
</template>

<script>
import PhotoGallery from './components/PhotoGallery'
import TimeLine from './components/TimeLine'
import Profile from './components/Profile'
import Blog from './components/Blog'
import Footer from './components/Footer'
import '@mdi/font/css/materialdesignicons.css'

export default {
    name: 'App',
    components: {
        PhotoGallery,
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
                easing: 'easeInOutCubic'
            }
        }
    }
}
</script>
