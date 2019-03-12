<template>
<v-layout align-center justify-center>
    <v-flex sm12>
        <div style="height:100vh">
            <div id="ityped" class="display-3 font-weight-light"></div>
        </div>
    </v-flex>
</v-layout>
</template>

<script>
import {
    init
} from 'ityped'

export default {
    data: () => ({
        images: [
            require('../assets/img1.jpg'),
            require('../assets/img2.jpg'),
            require('../assets/img3.jpg'),
            require('../assets/img4.jpg'),
        ],
        scrollOpt: {
            duration: 1500,
            offset: 10,
            easing: 'easeInOutCubic'
        }
    }),
    mounted: function() {
        init("#ityped", {
            // required - for now, only accepting texts
            strings: [
                'def sayThanks():',
                'print("Hello Canon\'s Page!")',
                'print("This is my profiles.")',
                'print("Thank\'s to visit!!")'
            ],
            //表示させる文字
            typeSpeed: 55, //default
            //表示する時のスピード
            backSpeed: 30, //default
            //戻る時のスピード
            startDelay: 500, //default
            //スタート時の遅延時間
            backDelay: 500, //default
            //戻る時の遅延時間
            loop: false, //default
            //ループの有無
            showCursor: true, //default
            //カーソル表示の有無
            cursorChar: "|", //default
            //カーソルの形状
            onFinished: function() {
                $vuetify.goTo('#eyecatch', this.scrollOpt)
            }
        });
    }
}
</script>
