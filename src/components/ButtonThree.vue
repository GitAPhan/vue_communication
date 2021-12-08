<template>
    <div>
        <!-- event listener @click to call click_emit function -->
        <button @click="click_emit">Button Three</button>
    </div>
</template>

<script>
    export default {
        name: 'button-three',
  methods: {
            // function to emit message to parent component
    click_emit() {
      this.$emit("clicked", "Button Three has been clicked!");
    },
  },
    }
</script>

<style scoped>

</style>