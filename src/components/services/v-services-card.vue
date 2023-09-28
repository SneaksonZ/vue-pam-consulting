<template>
    <div class="services__card services-card">
        <picture class="services-card__picture">
            <img :src="require('../../assets/images/home/' + card.image)" :alt="card.alt" class="services-card-picture__img">
        </picture>
        <div class="services-card-body">
            <h3 class="services-card-body__title"> {{ card.title }} </h3>
            <p class="services-card-body__text text"> {{ card.text }} </p>
            <v-button
                    class="intro__button"
                    :title=this.button.title
                    :isGradient=this.button.isGradient
            >
            {{ button.title }}
            </v-button>
        </div>
    </div>
</template>

<script>
import vButton from '../#helpers/v-button.vue'

export default {
    name: 'v-services-card',
    components: {
        vButton
    },
    props: {
        card: {
            type: Object,
            default() {
                return {};
            }
        }
    },
    data() {
        return {
            button: {
                title: 'Find Out More',
                isGradient: true
            }
        }
    }
}
</script>