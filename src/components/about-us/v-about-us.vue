<template>
    <section class="about-us">
        <div class="about-us__body">
            <div class="about-us__row">
                <div class="about-us-info about-us__info">
                    <h2 class="about-us-info__title title"> {{ block.title }} </h2>
                    <p class="about-us-info__text" v-html="block.text"></p>
                    <v-button class="about-us-info__button"
                        :title="block.button.title"
                        :isGradient="block.button.isGradient"
                    />
                </div>
                <v-about-us-card
                    :block="card"
                />
            </div>
        </div>
    </section>
</template>



<script>
import vAboutUsCard from './v-about-us-card'
import vButton from '../#helpers/v-button.vue';

export default {
    name: 'v-about-us',
    components: {
        vAboutUsCard,
        vButton
    },
    data() {
        return {
            block: {
                title: 'Who we are',
                text: 'PAM Consulting is built upon a team of motivated professionals aiming to provide families and businesses the services they need to relocate to the island of Cyprus. <br><br> We understand the challenges of deciding to relocate and this is why we prioritize our clients\' needs by making sure that the whole relocation process is as smooth and simple as possible.',
                button: {
                    title: 'More about us',
                    isGradient: false,
                }
            },
            card: {
                title: 'FOUNDER',
                subtitle: 'Anastasia Papaharidemou',
                image: {
                    src: 'about-us_founder-photo.png',
                    alt: 'founderPhoto'
                },
                button: {
                    title: 'Contact',
                    isGradient: false,
                }
            }
        }
    }
}
</script>