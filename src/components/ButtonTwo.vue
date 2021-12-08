<template>
    <div>
        <!-- event listener @click to call click_emit function -->
        <button @click="click_emit">Button Two</button>
    </div>
</template>

<script>
    export default {
        name: 'button-two',
  methods: {
            // function to emit message to parent component
    click_emit() {
      this.$emit("clicked", "Button Two has been clicked!");
    },
  },
    }
</script>

<style scoped>

</style>