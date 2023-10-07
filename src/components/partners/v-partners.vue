<template>
    <section class="partners" style="padding-bottom: 100px;">
        <div class="partners__body">
            <h2 class="partners__title title"> {{ block.title }} </h2>
            <div class="partners__icons partners-icons">
                <v-partners-icon
                    v-for="partner in block.partners"
                    :key="partner.id"
                    :icon="partner"
                />
            </div>
        </div>
    </section>
</template>


<script>
import vPartnersIcon from './v-partners-icon.vue';

export default {
    name: 'v-partners',
    components: {
        vPartnersIcon,
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