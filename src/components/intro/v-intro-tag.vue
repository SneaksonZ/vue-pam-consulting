<template>
    <div class="intro-tags-item">
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