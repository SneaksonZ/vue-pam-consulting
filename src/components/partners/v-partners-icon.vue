<template>
    <picture class="partners-icons-picture partners-icons__picture">
        <img
            class="partners-icons__img"
            :src="require('../../assets/images/home/' + icon.src)"
            :alt="icon.alt"
        >
    </picture>
</template>

<script>

export default {
    name: 'v-partners-icon',
    props: {
        icon: {
            type: Object,
            default() {
                return {};
            }
        }
    }
}

</script>