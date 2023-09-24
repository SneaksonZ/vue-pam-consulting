<template>
    <div class="wrapper">
        <v-intro></v-intro>
    </div>
</template>

<script>
import vIntro from './intro/v-intro.vue';

export default {
    name: 'v-wrapper',
    components: {
        vIntro
    }
}
</script>