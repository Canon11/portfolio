<template>
<div class="my-5">
    <div class="display-2 font-weight-regular font-italic text-sm-center">TimeLine</div>
    <v-timeline class="mt-4">
        <v-timeline-item v-for="(year, i) in years" :key="i" :color="year.color" small>
            <span slot="opposite" :class="`headline font-weight-bold ${year.color}--text`" v-text="year.year"></span>
            <v-card class="elevation-2">
                <v-card-title class="headline" v-text="year.title"></v-card-title>
                <v-card-text v-text="year.description"></v-card-text>
            </v-card>
        </v-timeline-item>
    </v-timeline>
</div>
</template>

<script>
export default {
    data: () => ({
        years: [{
                color: 'cyan',
                year: '2013',
                title: '筑波大学入学',
                description: '筑波大に入学し、情報学を学び始める。Javaを書きながらも理解に苦しみ、プログラミングに苦手意識を持ち始める。サークルはストリートダンス。'
            },
            {
                color: 'green',
                year: '2015',
                title: 'Web開発にのめり込む',
                description: 'PythonでWeb開発を初め、Webプログラミングの楽しさを知る。プログラミングが好きになる。院進するつもりだったが、大学卒業後の就職をここで決める。'
            },
            {
                color: 'pink',
                year: '2017',
                title: '大学卒業・新卒入社',
                description: '大学を卒業し、Web系ベンチャーに入社。ソーシャルゲームのサーバサイドエンジニアとしてバックエンド開発全般を担当するようになる。新規開発に苦しむ。'
            },
            {
                color: 'amber',
                year: '2018',
                title: '退職・起業',
                description: '新卒で入った会社を退職し、大学時代の先輩とその友達と株式会社を起業。受注開発やシステム開発をしながらも、収益アップに苦しむ（現在進行形）'
            }
        ]
    })
}
</script>
