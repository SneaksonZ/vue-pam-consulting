<template>
    <div class="about-us__founder-card about-us-founder-card">
        <img
                :src="require('../../assets/images/home/' + block.image.src)"
                :alt="block.image.alt"
                class="boxes-card-icon__img"
            >
        <div class="about-us-founder-card__column">
            <h4 class="about-us-founder-card__title"> {{ block.title }} </h4>
            <span class="about-us-founder-card__text"> {{ block.subtitle }} </span>
            <v-button class="about-us-founder-card__button"
                :title="block.button.title"
                :isGradient="block.button.isGradient"
            />
        </div>
    </div>
</template>

<script>

import vButton from '../v-button.vue';

export default {
    name: 'v-about-us-card',
    components: {
        vButton
    },
    props: {
        block: {
            type: Object,
            default() {
                return {};
            }
        }
    }
}

</script>