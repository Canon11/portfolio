<template>
<div class="my-5">
    <div class="display-2 font-weight-regular font-italic text-xs-center">Profile</div>
    <v-layout justify-center class="mt-4">
        <v-flex sm8>
            <v-card>
                <v-card-title>MyProfile</v-card-title>
                <v-card-text>My Name Is Kk</v-card-text>
            </v-card>
        </v-flex>
    </v-layout>
    <div class="text-xs-center">
        <v-menu offset-y>
            <v-btn slot="activator" color="primary" dark>
                Change
            </v-btn>
            <v-list>
                <v-list-tile v-for="(item, index) in items" :key="index" @click="">
                    <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                </v-list-tile>
            </v-list>
        </v-menu>
    </div>
</div>
</template>

<script>
export default {
    data: () => ({
        items: [{
                title: 'Click Me'
            },
            {
                title: 'Click Me'
            },
            {
                title: 'Click Me'
            },
            {
                title: 'Click Me 2'
            }
        ]
    })
}
</script>
