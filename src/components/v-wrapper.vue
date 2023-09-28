<template>
    <div class="wrapper">
        <v-intro />
        <v-services />
        <v-moving-to-paradise />
        
        <v-why-cyprus/>
        <v-make-it-happen/>

    </div>
</template>

<script>
import vIntro from './intro/v-intro.vue';
import vServices from './services/v-services.vue';
import vMovingToParadise from './moving-to-paradise/v-moving-to-paradise.vue';
import vMakeItHappen from './make-it-happen/v-make-it-happen.vue';
// 
import vWhyCyprus from './why-cyprus/v-why-cyprus.vue';


export default {
    name: 'v-wrapper',
    components: {
        vIntro,
        vServices,
        vMovingToParadise,
        vWhyCyprus,
        vMakeItHappen,
    },
}
</script>