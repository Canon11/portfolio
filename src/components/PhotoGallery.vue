<template>
<v-carousel hide-delimiters>
    <v-carousel-item v-for="(image, i) in images" :key="i" :src="image"></v-carousel-item>
</v-carousel>
</template>

<script>
export default {
    data: () => ({
        images: [
            'https://d1f5hsy4d47upe.cloudfront.net/9b/9b534625bee11de6210aa94dbd83ff24_w.jpg',
            'https://d1f5hsy4d47upe.cloudfront.net/36/3683fcd16a4c79e00b4339c951fcb5f4_w.jpg',
            'https://d1f5hsy4d47upe.cloudfront.net/27/2772d37f06e7d34c4204d42c50d35f57_w.jpg'
        ]
    })
}
</script>
