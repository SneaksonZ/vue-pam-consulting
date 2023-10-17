<template>
    <section class="partners">
        <div class="container">
            <div class="partners__body">
                <v-title
                    class="partners__title"
                    :text="block.title"
                />
                <div class="partners__icons partners-icons">
                    <v-partners-icon
                        class="partners-icons__picture"
                        v-for="partner in block.partners"
                        :key="partner.id"
                        :icon="partner"
                    />
                </div>
            </div>
        </div>
    </section>
</template>


<script>
import vTitle from '../.helpers/v-title.vue';
import vPartnersIcon from './v-partners-icon.vue';

export default {
    name: 'v-partners',
    components: {
        vTitle,
        vPartnersIcon
    },
    data() {
        return {
            block: {
                title: 'Our partners',
                partners: [
                    {
                        id: 1,
                        src:'partners-partner1.png',
                        alt:'partner1'
                    },
                    {
                        id: 2,
                        src:'partners-partner2.png',
                        alt:'partner2'
                    },
                    {
                        id: 3,
                        src:'partners-partner3.png',
                        alt:'partner3'
                    },
                    {
                        id: 4,
                        src:'partners-partner4.png',
                        alt:'partner4'
                    },
                    {
                        id: 5,
                        src:'partners-partner5.png',
                        alt:'partner5'
                    },
                    {
                        id: 6,
                        src:'partners-partner6.png',
                        alt:'partner6'
                    },
                ]
            }
        }
    },
}

</script>