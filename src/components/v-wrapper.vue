<template>
    <div class="wrapper">
        <v-intro/>
        <v-services/>
        <v-moving-to-paradise/>
        <v-boxes/>
    </div>
</template>

<script>
import vIntro from './intro/v-intro.vue';
import vServices from './services/v-services.vue';
import vMovingToParadise from './moving-to-paradise/v-moving-to-paradise.vue';
import vBoxes from './boxes/v-boxes.vue'

export default {
    name: 'v-wrapper',
    components: {
        vIntro,
        vServices,
        vMovingToParadise,
        vBoxes
    }
}
</script>