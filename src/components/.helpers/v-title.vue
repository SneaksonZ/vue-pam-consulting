<template>
    <h2
        class="title"
        :class="computedClasses"
    >
        {{ text }}
    </h2>
</template>

<script>
export default {
    name: "v-title",
    props: {
        text: {
            type: String,
            require: true,
        },
        needsUnderline: {
            type: Boolean,
            default: false,
        },
        needsMobileCapitalize: {
            type: Boolean,
            default: false,
        }
    },
    computed: {
        computedClasses() {
            return {
                'title_underline': this.needsUnderline,
                'title_capitalize': this.needsMobileCapitalize
            };
        }
    }
}
</script>