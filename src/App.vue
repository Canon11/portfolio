<template>
<v-app>
    <v-toolbar app dark class="indigo">
        <v-toolbar-title class="headline">
            <span>Canon's Page</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items>
            <v-btn flat>
                <v-icon>mdi-timeline</v-icon>TimeLines
            </v-btn>
            <v-btn flat>
                <v-icon>mdi-face-profile</v-icon>Profiles
            </v-btn>
            <v-btn flat>
                <v-icon>mdi-new-box</v-icon>New Blogs
            </v-btn>
        </v-toolbar-items>
    </v-toolbar>

    <v-content>
        <PhotoGallery />
        <TimeLine />
        <Profile />
        <Blog />
    </v-content>

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
            //
        }
    }
}
</script>
