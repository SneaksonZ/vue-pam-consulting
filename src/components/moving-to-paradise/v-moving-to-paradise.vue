<template>
    <section class="moving-to-paradise">
        <picture class="moving-to-paradise__picture">
            <source :srcset="require('../../assets/images/home/' + image1.mobile)" media="(max-width: 480px)">
            <source :srcset="require('../../assets/images/home/' + image1.mini)" media="(max-width: 950px)">
            <img :src="require('../../assets/images/home/' + image1.default)" v-bind:alt="image1.alt" class="moving-to-paradise-picture__img">
        </picture>
        <div class="moving-to-paradise__body">
            <h1 class="moving-to-paradise__title title"> {{ block.title }}</h1>
            <p class="moving-to-paradise__text text" v-html="block.text"></p>
            <v-button
                class="moving-to-paradise__button"
                :title="block.button.title"
                :isGradient="block.button.isGradient"
            />
        </div>
        <picture class="moving-to-paradise__picture">
            <source :srcset="require('../../assets/images/home/' + image2.mobile)" media="(max-width: 480px)">
            <source :srcset="require('../../assets/images/home/' + image2.mini)" media="(max-width: 950px)">
            <img :src="require('../../assets/images/home/' + image2.default)" v-bind:alt="image2.alt" class="moving-to-paradise-picture__img">
       </picture>
    </section>
</template>

<script>
import vButton from '../#helpers/v-button.vue'

export default {
    name: 'v-moving-to-paradise',
    components: {
        vButton
    },
    data() {
        return {
            block: {
                title: 'Moving to Paradise',
                text: `Have you ever dreamed about the perfect place to live? Your
                definition of perfect may be different someone else's. Are you longing to live by the beach and
                listen to the soothing waves or are you a kind of person who enjoys the bustling sounds of the
                city? Whatever lifestyle you desire, Cyprus has it all! Whether you're travelling with your
                family, your partner, or as a solo business entrepreneur, this exotic island can offer you a
                little bit of everything.
                <br>
                <br>
                If you've made the decision to relocate to Cyprus, then you are expecting to find a safe place
                to settle. With extremely low crime rate, stunning sandy beaches, and awe-inspiring mountain
                views, Cyprus is the place to be!`,
                button: {
                    title : 'Find Out More',
                    isGradient: true
                }
            },
            image1: {
                default: 'moving-to-paradise_villa1.jpg',
                mobile: 'moving-to-paradise_villa1_mobile.jpg',
                mini: 'moving-to-paradise_villa1_mini.jpg',
                alt: 'villa1'
            },
            image2: {
                default: 'moving-to-paradise_villa2.jpg',
                mobile: 'moving-to-paradise_villa2_mobile.jpg',
                mini: 'moving-to-paradise_villa2_mini.jpg',
                alt: 'villa2'
            }
        }
    }
}
</script>