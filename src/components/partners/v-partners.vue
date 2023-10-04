<template>
    <section class="partners" style="padding-bottom: 100px;">
        <div class="partners__body">
            <h2 class="partners__title title"> {{ block.title }} </h2>
            <div class="partners__icons partners-icons">
                <v-carousel>
                    <v-partners-icon
                        v-for="partner in block.partners"
                        :key="partner.key"
                        :icon="partner"
                    />
                </v-carousel>
            </div>
        </div>
    </section>
</template>


<script>
import vPartnersIcon from './v-partners-icon.vue';
import vCarousel from '../.helpers/v-carousel.vue';

export default {
    name: 'v-partners',
    components: {
        vPartnersIcon,
        vCarousel
    },
    data() {
        return {
            block: {
                title: 'Our partners',
                partners: [
                    {
                        src:'partners-partner1.png',
                        alt:'partner1'
                    },
                    {
                        src:'partners-partner2.png',
                        alt:'partner2'
                    },
                    {
                        src:'partners-partner3.png',
                        alt:'partner3'
                    },
                    {
                        src:'partners-partner4.png',
                        alt:'partner4'
                    },
                    {
                        src:'partners-partner5.png',
                        alt:'partner5'
                    },
                    {
                        src:'partners-partner6.png',
                        alt:'partner6'
                    },
                ]
            }
        }
    },
}

</script>