<template>
  <div>
        <!-- event listener @click to call click_emit function -->
    <button @click="click_emit">Button One</button>
  </div>
</template>

<script>
export default {
  name: "button-one",
  methods: {
            // function to emit message to parent component
    click_emit() {
      this.$emit("clicked", this.button_message);
    },
    // function to change button_message variable to reflect party button being clicked
    clicked_function() {
        this.button_message = "Button One has been clicked and It's PARTY TIME!"
    }
  },
  mounted () {
    //   to grab global event 'partyButtonClicked' from $root and call clicked_function function
      this.$root.$on('partyButtonClicked', this.clicked_function);
  },
  data() {
      return {
        //   button_message varaible containing the button message 
          button_message: "Button One has been clicked!",
      }
  },
};
</script>

<style scoped>
</style>