<template>
    <section class="map">
        <div class="container">
            <div class="map__body">
                <div class="map__column">
                    <v-title
                        class="map__title"
                        :text="block.title"
                    />
                    <h5 class="map__subtitle" v-if="isMobile"> {{ block.subtitle.mobile }} </h5>
                    <h5 class="map__subtitle" v-else> {{ block.subtitle.desktop }} </h5>
                    <picture class="map__picture">
                        <img :src="require('../../assets/images/home/' + block.image.src)" :alt="block.image.alt" class="map__img">
                    </picture>
                </div>
                <div class="map__column">
                    <v-map-card :card="cards[0]" />
                </div>
            </div>
        </div>
    </section>
</template>


<script>
import vTitle from '../.helpers/v-title.vue';
import vMapCard from './v-map-card.vue';

export default {
    name: 'v-map',
    components: {
        vTitle,
        vMapCard
    },
    data() {
        return {
            isMobile: true,
            block: {
                title: 'FIND THE IDEAL LOCATION TO CALL HOME',
                subtitle: {
                    desktop: 'Click your mouse over any city to learn more about it',
                    mobile: 'Tap on any city to learn more about it',
                },
                image: { 
                    src: 'map.png',
                    alt: 'map',
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
                            src: 'map-card_limassol-image_1.jpg',
                            alt: 'limassol1',
                        },
                        {
                            src: 'map-card_limassol-image_2.jpg',
                            alt: 'limassol2',
                        },
                        {
                            src: 'map-card_limassol-image_3.jpg',
                            alt: 'limassol3',
                        },
                    ]
                }]
        }
    },
    created() {
        this.isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);
    },
}
</script>