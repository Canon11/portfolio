<template>
<v-container>
    <div class="display-2 font-weight-regular font-italic text-sm-center">Blogs</div>
    <v-layout row justify-space-around>
        <v-flex sm3 v-for="(blog, i) in blogs" :key="i">
            <v-card>
                <v-img src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg" height="200px">
                </v-img>

                <v-card-title primary-title>
                    <div>
                        <div class="headline">{{ blog.title }}</div>
                        <span class="grey--text">1,000 miles of wonder</span>
                    </div>
                </v-card-title>

                <v-card-actions>
                    <v-btn flat>Share</v-btn>
                    <v-btn flat color="purple">Explore</v-btn>
                    <v-spacer></v-spacer>
                    <v-btn icon @click="blog.show = !blog.show">
                        <v-icon>{{ blog.show ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
                    </v-btn>
                </v-card-actions>

                <v-slide-y-transition>
                    <v-card-text v-show="blog.show">{{ blog.description }}</v-card-text>
                </v-slide-y-transition>
            </v-card>
        </v-flex>
    </v-layout>
</v-container>
</template>

<script>
export default {
    data: () => ({
        show: false,
        blogs: [{
                title: 'blog1',
                description: 'desc1',
                show: false
            },
            {
                title: 'blog2',
                description: 'desc2',
                show: false
            },
            {
                title: 'blog3',
                description: 'desc3',
                show: false
            }
        ]
    })
}
</script>
