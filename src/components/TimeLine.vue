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
                year: '1960',
                title: 'text1',
                description: 'description 1aweofijaweofiwaofijawoefijaowifjawe'
            },
            {
                color: 'green',
                year: '1970',
                title: 'text2',
                description: 'description 2'
            },
            {
                color: 'pink',
                year: '1980',
                title: 'text3',
                description: 'description 3'
            },
            {
                color: 'amber',
                year: '1990',
                title: 'text4',
                description: 'description 4'
            },
            {
                color: 'orange',
                year: '2000',
                title: 'text5',
                description: 'description 5'
            }
        ]
    })
}
</script>
