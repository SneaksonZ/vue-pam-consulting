<template>
    <v-boxes
        :block="block"
        :cards="boxes"
    />
</template>

<script>
import vBoxes from '../.helpers/boxes/v-boxes.vue';

export default {
    name: 'v-why-cyprus',
    components: {
        vBoxes
    },
    data() {
        return {
            block: {
                title:  
                { 
                    text:'Why Choose Cyprus?',
                    mobileCapitalize: true,
                },
                subtitle: 'When you\'re searching for the ideal home you want everything to be perfect. This is why over the years more and more people from all around the world are choosing Cyprus as their ultimate destination. This smal Mediterranean mesmerizes millions of visitors every year.',
            },
            boxes: [
                {
                    image: 'box_tax.png',
                    alt: 'tax',
                    title: 'Progressive tax system',
                    subtitle: 'Offering one of the most attractive tax regimes in Europe',
                },
                {
                    image: 'box_weather-and-climate.png',
                    alt: 'stunning_weather',
                    title: 'Stunning weather and climate',
                    subtitle: 'Enjoy a high quality of life with over 324 days of sun annually',
                },
                {
                    image: 'box_expat-community.png',
                    alt: 'blooming_community',
                    title: 'Blooming expat community',
                    subtitle: 'Become part of an increasingly diverse community',
                },
                {
                    image: 'box_fimily-oriented.png',
                    alt: 'family_oriented',
                    title: 'Family-oriented values',
                    subtitle: 'Excellent education standards and extremely low crime rates',
                },
            ]
        }
    },
}
</script>