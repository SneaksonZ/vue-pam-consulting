<template>
    <input
        :type="block.type"
        :name="block.name"
        :placeholder="block.placeholder"
        :tabindex="block.tabindex"
    />
</template>

<script>
export default {
    name: 'v-form-input',
    components: {
    },
    props: {
        block: {
            type: Object,
            default() {
                return {
                    
                }
            }
        }
    }
}
</script>