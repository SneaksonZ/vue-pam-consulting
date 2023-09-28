<template>
    <div class="wrapper">
        <v-intro />
        <v-services />
        <v-moving-to-paradise />
        <v-why-cyprus/>
        <v-about-us/>
        <v-make-it-happen/>
        <v-contact-us/>
    </div>
</template>

<script>
import vIntro from './intro/v-intro.vue';
import vServices from './services/v-services.vue';
import vMovingToParadise from './moving-to-paradise/v-moving-to-paradise.vue';
import vMakeItHappen from './make-it-happen/v-make-it-happen.vue';
// 
import vAboutUs from './about-us/v-about-us.vue'
import vWhyCyprus from './boxes/v-why-cyprus.vue';
import vContactUs from './contact-us/v-contact-us.vue'
// import vBoxes from './boxes/v-boxes.vue';

export default {
    name: 'v-wrapper',
    components: {
        vIntro,
        vServices,
        vMovingToParadise,
        vWhyCyprus,
        vMakeItHappen,
        vAboutUs,
        vContactUs

    },
}
</script>