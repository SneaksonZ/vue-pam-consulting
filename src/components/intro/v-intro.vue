<template>
    <section class="intro">
            <swiper-container 
                class="intro-swiper"
                :effect="'fade'"
                :autoplay-delay="6000"
            >
                <swiper-slide class="intro__slide" v-for="block in blocks" :key="block.id">
                    <picture class="intro-bg intro__bg">
                        <source :srcset="require('../../assets/images/backgrounds/' + block.backgroundImage.mobile)" media="(max-width: 479px)">
                        <source :srcset="require('../../assets/images/backgrounds/' + block.backgroundImage.mini)" media="(max-width: 767px)">
                        <source :srcset="require('../../assets/images/backgrounds/' + block.backgroundImage.medium)" media="(max-width: 999px)">
                        <img :src="require('../../assets/images/backgrounds/' + block.backgroundImage.default)" alt="intro-bg" class="intro-bg__img">
                </picture>
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
                                class="intro-titles intro_titles"
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
import 'swiper/css';
import 'swiper/css/effect-fade';
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
            swiperParams: {
                rewind: true,
                parallax: true,
                speed: 800,
                pagination: {
                    clickable: true,
                },
                effect: 'fade',
                fadeEffect: {
                    crossFade: true
                },
                breakpoints: {
                    1000: {
                        allowTouchMove: true,
                    },
                    0: {
                        allowTouchMove: false,
                    },
                },
                on: {
                    init() {
                        // ...
                    },
                },
            },
            blocks: [
                {
                    id: "I0",
                    backgroundImage: {
                        default: 'bg-intro-relocation.jpg',
                        medium: 'bg-intro-relocation-medium.jpg',
                        mini: 'bg-intro-relocation-mini.jpg',
                        mobile: 'bg-intro-relocation-mobile.jpg',
                    },
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
                            image: 'intro-cities_1.jpg',
                            alt: 'Nicosia',
                            subtitle: 'Nicosia'
                        },
                        {
                            id: 'C01',
                            image: 'intro-cities_2.jpg',
                            alt: 'Limassol',
                            subtitle: 'Limassol'
                        },
                        {
                            id: 'C02',
                            image: 'intro-cities_3.jpg',
                            alt: 'Paphos',
                            subtitle: 'Paphos'
                        },
                        {
                            id: 'C03',
                            image: 'intro-cities_4.jpg',
                            alt: 'Larnaka',
                            subtitle: 'Larnaka'
                        }
                    ]
                },
                {
                    id: "I1",
                    backgroundImage: {
                        default: 'bg-intro-invest.jpg',
                        medium: 'bg-intro-invest-medium.jpg',
                        mini: 'bg-intro-invest-mini.jpg',
                        mobile: 'bg-intro-invest-mobile.jpg',
                    },
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
                    backgroundImage: {
                        default: 'bg-intro-family-relocation.jpg',
                        medium: 'bg-intro-family-relocation-medium.jpg',
                        mini: 'bg-intro-family-relocation-mini.jpg',
                        mobile: 'bg-intro-family-relocation-mobile.jpg',
                    },
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
                    backgroundImage: {
                        default: 'bg-intro-business-relocation.jpg',
                        medium: 'bg-intro-business-relocation-medium.jpg',
                        mini: 'bg-intro-business-relocation-mini.jpg',
                        mobile: 'bg-intro-business-relocation-mobile.jpg',
                    },
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
                    backgroundImage: {
                        default: 'bg-intro-yachts-investments.jpg',
                        medium: 'bg-intro-yachts-investments-medium.jpg',
                        mini: 'bg-intro-yachts-investments-mini.jpg',
                        mobile: 'bg-intro-yachts-investments-mobile.jpg',
                    },
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
                    backgroundImage: {
                        default: 'bg-intro-moving-cyprus.jpg',
                        medium: 'bg-intro-moving-cyprus-medium.jpg',
                        mini: 'bg-intro-moving-cyprus-mini.jpg',
                        mobile: 'bg-intro-moving-cyprus-mobile.jpg',
                    },
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
    },
    mounted() {
        const swiperEl = document.querySelector('.intro-swiper');
        Object.assign(swiperEl, this.swiperParams);
        swiperEl.initialize();
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