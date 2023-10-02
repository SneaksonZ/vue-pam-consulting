<template>
    <ul class="header-navigation-item-dropdown-menu">
        <li class="header-navigation-item-dropdown-menu__item header-navigation-item-dropdown-menu-item"
            v-for="link in this.link.sublinks"
            :key="link.key"
        >
            <v-header-link 
                class="header-navigation-item-dropdown-menu-item__link"
                :link="link"
            />
        </li>
    </ul>
</template>

<script>
import vHeaderLink from './v-header-link.vue';

export default {
    name: 'v-header-dropdown',
    components: {
        vHeaderLink
    },
    props: {
        link: {
            type: Object,
            default() {
                return {};
            }
        }
    }
}
</script>