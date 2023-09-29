<template>
    <div class="wrapper">
        <v-intro />
        <v-services />
        <v-moving-to-paradise />
        <v-why-cyprus/>
        <v-map/>
        <v-about-us/>
        <v-make-it-happen/>
        <v-contact-us/>
        <v-partners/>
    </div>
</template>

<script>
import vIntro from './intro/v-intro.vue';
import vServices from './services/v-services.vue';
import vMovingToParadise from './moving-to-paradise/v-moving-to-paradise.vue';
import vWhyCyprus from './why-cyprus/v-why-cyprus.vue';
import vMap from './map/v-map.vue';
import vAboutUs from './about-us/v-about-us.vue';
import vMakeItHappen from './make-it-happen/v-make-it-happen.vue';
import vContactUs from './contact-us/v-contact-us.vue';
import vPartners from './partners/v-partners.vue';

export default {
    name: 'v-wrapper',
    components: {
        vIntro,
        vServices,
        vMovingToParadise,
        vWhyCyprus,
        vMap,
        vAboutUs,
        vMakeItHappen,
        vContactUs,
        vPartners

    },
}
</script>