<template>
    <section class="map">
        <div class="map__body">
            <div class="map__column">
                <h3 class="map__title"> {{ block.title }} </h3>
                <h5 class="map__subtitle" v-if="isDesktop"> {{ block.subtitle.largeScreen }} </h5>
                <h5 class="map__subtitle" v-else> {{ block.subtitle.smallScreen }} </h5>
                <div class="map__selector">
                    <picture class="map__picture">
                        <img :src="require('../../assets/images/home/' + block.image.src)" :alt="block.image.alt" class="map__img">
                    </picture>
                </div>
            </div>
            <div class="map__column">
                <v-map-card :card="cards[0]" />
            </div>
        </div>
    </section>
</template>


<script>

import vMapCard from './v-map-card.vue';

export default {
    name: 'v-map',
    components: {
        vMapCard,
    },
    data() {
        return {
            isDesktop: true,
            block: {
                title: 'FIND THE IDEAL LOCATION TO CALL HOME',
                subtitle: {
                    largeScreen: 'Click your mouse over any city to learn more about it',
                    smallScreen: 'Tap on any city to learn more about it'
                },
                image: { 
                    src: 'map.png',
                    alt: 'map'
                }
            },
            cards: [
                {
                    title: 'Limassol',
                    text: `The sunny city of Limassol is the second largest city of the island, and it is among the
							most desirable travel and business destinations both for families and for entrepreneurs
							looking to expand their business horizons. The combination of elegant accommodation and
							ancient architectural views is bound to capture the interest of people of any age.
							<br>
							<br>
							The Limassol Marina is the first marina to harbor yachts in Cyprus and it is surrounded
							by renowned bars and restaurants. The residents of Limassol pride themselves on their
							cultural values and festivities as hundreds of theatrical performances take place each
							year at the Rialto theater, and the city holds an annual Wine Festival and Carnival
							Parade.`,
                    images: [
                        {
                            src: 'map-card_limassol-image_1.png',
                            alt: 'limassol1'
                        },
                        {
                            src: 'map-card_limassol-image_2.png',
                            alt: 'limassol2'
                        },
                        {
                            src: 'map-card_limassol-image_3.png',
                            alt: 'limassol3'
                        }
                    ]
                }]
        }
    },
    created() {
        window.addEventListener('resize', this.onResize);
        this.onResize();
    },
    destroyed() {
        window.removeEventListener('resize', this.onResize)
    },
    methods: {
        onResize() {
            this.isDesktop = window.innerWidth > 1200;
        }
    }
}
</script>