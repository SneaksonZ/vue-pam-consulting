<template>
    <section class="about-us">
        <div class="container">
            <div class="about-us__wrapper">
                <div class="about-us__row">
                    <div class="about-us-info about-us__info">
                        <v-title
                            class="about-us-info__title"
                            :text="block.title"
                            :needsUnderline="true"  
                        />
                        <p class="about-us-info__text text" v-html="block.text"></p>
                        <v-button class="about-us-info__button"
                            :title="block.button.title"
                            :isGradient="block.button.isGradient"
                        />
                    </div>
                    <v-about-us-card
                        class="about-us__founder-card"
                        :block="card"
                    />
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import vTitle from '../.helpers/v-title.vue';
import vButton from '../.helpers/v-button.vue';
import vAboutUsCard from './v-about-us-card';

export default {
    name: 'v-about-us',
    components: {
        vTitle,
        vButton,
        vAboutUsCard,
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
                    src: 'about-us_founder-photo.jpg',
                    alt: 'founderPhoto',
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