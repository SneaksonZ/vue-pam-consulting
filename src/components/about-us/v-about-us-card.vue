<template>
    <div class="about-us-founder-card">
        <img
            class="about-us-founder-card__image"
            :src="require('../../assets/images/home/' + block.image.src)"
            :alt="block.image.alt"
        >
        <div class="about-us-founder-card__body">
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

import vButton from '../.helpers/v-button.vue';

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