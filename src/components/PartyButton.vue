<template>
    <div>
        <!-- event listener @click to call button_clicked function -->
        <button @click="button_clicked">Party Button</button>
    </div>
</template>

<script>
    export default {
        name: 'party-button',
        methods: {
            // function to emit message to $root
            button_clicked() {
                this.$root.$emit('partyButtonClicked', "IT'S PARTY TIME!!!")
            }
        },
    }
</script>

<style scoped>

</style>