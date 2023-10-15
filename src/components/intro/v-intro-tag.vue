<template>
    <div class="intro-tags-item intro-tags__item">
        {{ tag.text }}
    </div>
</template>

<script>


export default {
    name: 'v-intro-tag',
    props: {
        tag: {
            type: Object,
            default() {
                return {};
            }
        }
    }
}
</script>