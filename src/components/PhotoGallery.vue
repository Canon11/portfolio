<template>
<v-carousel hide-delimiters>
    <v-carousel-item v-for="(image, i) in images" :key="i" :src="image"></v-carousel-item>
</v-carousel>
</template>

<script>
export default {
    data: () => ({
        images: [
            require('../assets/img1.jpg'),
            require('../assets/img2.jpg'),
            require('../assets/img3.jpg'),
            require('../assets/img4.jpg'),
        ]
    })
}
</script>
