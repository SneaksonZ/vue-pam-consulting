<template>
    <header class="header">
        <div class="header__body">
            <div class="header__wrapper">
                <img src="../../assets/images/base/logo.svg" alt="logo" class="header__logo">
                <ul class="header__navigation header-navigation"
                    :class="{'header-navigation_active': isBurgerActive}"    
                >
                    <li class="header-navigation__item header-navigation-item"
                        v-for="link in links"
                        :key="link.key"
                        :class="{ 'header-navigation-item-dropdown': link.sublinks.length }"
                        >
                        <v-header-link
                            class="header-navigation-item__link"
                            :link = "link"
                        />
                        <v-header-dropdown 
                            v-if="isDesktopVersion && link.sublinks.length"
                            :link = "link"
                        />
                    </li>
                </ul>
                <div class="header__buttons">
                    <v-button
                        class="header__button"
                        :title="button.text"
                        :isGradient="button.isGradient"
                    />
                    <button class="header-navigation-burger header-navigation__burger"
                        @click="isBurgerActive = !isBurgerActive"
                        :class="{'header-navigation-burger_active': isBurgerActive}"
                    >
                        <span class="header-navigation-burger__icon"></span>
                    </button>
                </div>
            </div>
        </div>
    </header>
</template>


<script>
import vHeaderLink from './v-header-link.vue';
import vHeaderDropdown from './v-header-dropdown.vue';
import vButton from '../.helpers/v-button.vue';

export default {
    name: 'v-header',
    components: {
        vHeaderLink,
        vHeaderDropdown,
        vButton
    },
    data() {
        return {
            isMobiVersion: false,
            isBurgerActive: false,
            button: {
                text: 'Get in touch',
                isGradient: false
            },
            links: [
                {
                    text: 'Home',
                    url: '#',
                    sublinks: []
                },
                {
                    text: 'About us',
                    url: '#',
                    sublinks: []
                },
                {
                    text: 'Services',
                    url: '#',
                    sublinks: [
                        {
                            text: 'Investments opportunities',
                            url: '#'
                        },
                        {
                            text: 'Business relocation',
                            url: '#'
                        },
                        {
                            text: 'Family relocation',
                            url: '#'
                        }
                    ]
                },
                {
                    text: 'Invest in Cyprus',
                    url: '#',
                    sublinks: [],
                },
                {
                    text: 'Migration',
                    url: '#',
                    sublinks: [],
                },
                {
                    text: 'Contact us',
                    url: '#',
                    sublinks: [],
                }
            ]

        }
    },
    created() {
        window.addEventListener('resize', this.onResize);
        this.onResize();
    },
    destroyed() {
        window.removeEventListener('resize', this.onResize)
    },
    methods: {
        onResize() {
            this.isDesktopVersion = window.innerWidth >= 1250;
        }
    }
}

</script>