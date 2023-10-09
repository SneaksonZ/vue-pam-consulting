<template>
    <section class="intro">
        <swiper-container 
            class="intro-swiper"

            :autoplay-delay="5000"
            :speed="600"
            :slides-per-view="1"
            :rewind="true"
            :effect="'fade'"
            :parallax="true"
            :pagination-clickable="true"
        >
            <swiper-slide class="intro__slide" v-for="block in blocks" :key="block.id">
                <img :src="require('../../assets/images/backgrounds/' + block.backgroundImage)" alt='intro-bg' class="intro__bg">
                <!-- <div class="intro__bg" style="background-image: url('../../assets/images/backgrounds/home-header-bg.jpg')"></div> -->
                <div class="intro__body">
                    <div class="intro__header">
                        <div 
                            class="intro__tags intro-tags"
                            data-swiper-parallax="-150"
                        >
                            <v-intro-tag
                                v-for="tag in block.tags"
                                :key="tag.id"
                                :tag="tag"
                                :class="{'intro-tags__item_dark':block.isColorsBlack}"
                            />
                        </div>
                        <div 
                            class="intro-titles"
                            :class="{'intro-titles_dark':block.isColorsBlack}"
                            data-swiper-parallax="-200"
                        >
                            <h1 class="intro__title title"> {{ block.title }} </h1>
                            <h4 
                                v-if="block.subtitle != ''"
                                class="intro__subtitle"
                            > {{ block.subtitle }} </h4>
                        </div>
                        <p 
                            class="intro__text text"
                            :class="{'intro__text_dark':block.isColorsBlack}"
                            data-swiper-parallax="-250"
                        > {{ block.text }} </p>
                        <v-button
                            data-swiper-parallax="-300"
                            class="intro__button"
                            :title="block.button.title"
                            :isGradient="block.button.isGradient"
                        />
                    </div>
                    <div class="intro-cities"
                        data-swiper-parallax="-400"
                    >
                        <h4 class="intro-cities__title title" v-if="block.cards.length != 0">Most popular cities</h4>
                        <div class="intro-cities__row">
                            <v-intro-card
                                v-for="card in block.cards"
                                :key="card.id"
                                :card="card"
                            />
                        </div>
                    </div>
                </div>
            </swiper-slide>
        </swiper-container>
    </section>
</template>

<script>
import vButton from '../.helpers/v-button.vue';
import vIntroTag from './v-intro-tag.vue';
import vIntroCard from './v-intro-card.vue';
import { register } from 'swiper/element/bundle';

register();

export default {
    name: 'v-intro',
    components: {
        vButton,
        vIntroTag,
        vIntroCard
    },
    data() {
        return {
            blocks: [
                {
                    id: "I0",
                    backgroundImage: 'bg-intro-relocation.jpg',
                    title: 'Relocation to Cyprus',
                    subtitle: 'Seamless - Exceptional - Experience',
                    text: 'The captivating Mediterranean island of Cyprus has become a business haven with a flourishing expat community. The strategic location that grants networking opportunities and the stability of being in the EU offers entrepreneurs the abilities they need to thrive.',
                    isColorsBlack: false,
                    button: {
                        title : 'Find Out More',
                        isGradient: true
                    },
                    tags: [
                        {
                            id: 'T0',
                            text: 'Investments'
                        },
                        {
                            id: 'T1',
                            text: 'Business relocation'
                        },
                        {
                            id: 'T2',
                            text: 'Family relocation'
                        }
                    ],
                    cards: [
                        {
                            id: 'C00',
                            image: 'intro-cities_1.png',
                            alt: 'Nicosia',
                            subtitle: 'Nicosia'
                        },
                        {
                            id: 'C01',
                            image: 'intro-cities_2.png',
                            alt: 'Limassol',
                            subtitle: 'Limassol'
                        },
                        {
                            id: 'C02',
                            image: 'intro-cities_3.png',
                            alt: 'Paphos',
                            subtitle: 'Paphos'
                        },
                        {
                            id: 'C03',
                            image: 'intro-cities_4.png',
                            alt: 'Larnaka',
                            subtitle: 'Larnaka'
                        }
                    ]
                },
                {
                    id: "I1",
                    backgroundImage: 'bg-intro-invest.jpg',
                    title: 'Invest in property in Cyprus',
                    subtitle: '',
                    text: 'Real estate has become a flourishing type of investment on the island, with an increasing number of people seeking to invest in residential and commercial property projects in Cyprus. With a confident and stable economic outlook, it is a great time to consider investing in Cyprus property.',
                    isColorsBlack: true,
                    button: {
                        title : 'Check more',
                        isGradient: true
                    },
                    tags: [
                        {
                            id: 'T10',
                            text: 'Investments'
                        },
                        {
                            id: 'T11',
                            text: 'Business relocation'
                        },
                        {
                            id: 'T12',
                            text: 'Family relocation'
                        }
                    ],
                    cards: [
                    ]
                },
                {
                    id: "I2",
                    backgroundImage: 'bg-intro-family-relocation.jpg',
                    title: 'Family Relocation',
                    subtitle: '',
                    text: 'Globally known as one of the safest places to live in the world, Cyprus is the ideal location for families. The healthy lifestyle and family-friendly communities have much to offer to every member of your family.',
                    isColorsBlack: true,
                    button: {
                        title : 'Check more',
                        isGradient: true
                    },
                    tags: [
                        {
                            id: 'T20',
                            text: 'Investments'
                        },
                        {
                            id: 'T21',
                            text: 'Business relocation'
                        },
                        {
                            id: 'T22',
                            text: 'Family relocation'
                        }
                    ],
                    cards: [
                    ]
                },
                {
                    id: "I3",
                    backgroundImage: 'bg-intro-business-relocation.jpg',
                    title: 'Business Relocation',
                    subtitle: '',
                    text: 'Cyprus has a lot to offer for business entrepreneurs who aim to reach for more and expand their business goals. The attractive tax benefits and office locations have transformed Cyprus into a country with endless business opportunities for everyone.',
                    isColorsBlack: false,
                    button: {
                        title : 'Check more',
                        isGradient: true
                    },
                    tags: [
                        {
                            id: 'T30',
                            text: 'Investments'
                        },
                        {
                            id: 'T31',
                            text: 'Business relocation'
                        },
                        {
                            id: 'T32',
                            text: 'Family relocation'
                        }
                    ],
                    cards: [
                    ]
                },
                {
                    id: "I4",
                    backgroundImage: 'bg-intro-yachts-investments.jpg',
                    title: 'Investing in Yachts',
                    subtitle: '',
                    text: 'Living on an island is an adventure that opens up a wide range of experiences and possibilities. Here, you can conquer the Mediterranean Sea by renting or owning a yacht as part of your investment plan.',
                    isColorsBlack: true,
                    button: {
                        title : 'Check more',
                        isGradient: true
                    },
                    tags: [
                        {
                            id: 'T40',
                            text: 'Investments'
                        },
                        {
                            id: 'T41',
                            text: 'Business relocation'
                        },
                        {
                            id: 'T42',
                            text: 'Family relocation'
                        }
                    ],
                    cards: [
                    ]
                },
                {
                    id: "I5",
                    backgroundImage: 'bg-intro-moving-cyprus.jpg',
                    title: 'Moving to Cyprus',
                    subtitle: '',
                    isColorsBlack: false,
                    text: 'Thousands of individuals and families from every part of the globe have immigrated to Cyprus after discovering their perfect place to call home. The island is now one of the most dominant destinations with huge expat communities.',
                    button: {
                        title : 'Check more',
                        isGradient: true
                    },
                    tags: [
                        {
                            id: 'T50',
                            text: 'Investments'
                        },
                        {
                            id: 'T51',
                            text: 'Business relocation'
                        },
                        {
                            id: 'T52',
                            text: 'Family relocation'
                        }
                    ],
                    cards: [
                    ]
                }
            ],
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../../helpers/swiper-pagination.scss';

swiper-container::part(pagination) {
    display: flex;
    align-items: center;
    flex-direction: column;
    top: 50%;
    transform: translate(0, -50%);
    right: 10.5%;
}

swiper-container::part(bullet) {
    width: em(12);
    height: em(12);
    border: 2px solid white;
    margin: em(6) 0;
}
    
swiper-container::part(bullet-active) {
    width: em(20);
    height: em(20);
    background-color: white;
    margin: em(6) 0;
}

@media (max-width: 767px) {
    swiper-container::part(pagination) {
        flex-direction: row;
        top: auto;
        bottom: 40px;
        right: 50%;
        transform: translate(50%, 0);
    }

    swiper-container::part(bullet) {
        width: em(12);
        height: em(12);
        border: 2px solid white;
        margin: 0 em(6);
    }
        
    swiper-container::part(bullet-active) {
        width: em(20);
        height: em(20);
        background-color: white;
        margin: 0 em(6);
    }
}

</style>