<template>
    <a :href="link.url" class="header-navigation-item-link"> {{ link.text }} </a>
</template>

<script>
export default {
    name: 'v-header-link',

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