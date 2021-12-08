<template>
  <div>
      <!-- @clicked is the emitted event from the child component, to call clicked_function function to add message to h1 -->
    <button-one @clicked="clicked_function"></button-one>
    <button-two @clicked="clicked_function"></button-two>
    <button-three @clicked="clicked_function"></button-three>
    <!-- party button tag -->
    <party-button></party-button>
    <!-- h1 tag with clicked_message varaible -->
    <h1>{{ clicked_message }}</h1>
  </div>
</template>

<script>
// imports from child components
import ButtonOne from "./ButtonOne.vue";
import ButtonTwo from "./ButtonTwo.vue";
import ButtonThree from "./ButtonThree.vue";
import PartyButton from "./PartyButton.vue";
export default {
  name: "home-content",
  components: {
    ButtonOne,
    ButtonTwo,
    ButtonThree,
    PartyButton,
  },
  methods: {
    //   function to define clicked_message variable with 'payload'
      clicked_function(payload) {
      this.clicked_message = payload;
      }
  },
  data() {
    return {
        // undefined variable to change when clicked_function has been called
      clicked_message: undefined,
    };
  },
  mounted () {
    //   to grab global event 'partyButtonClicked' from $root and call clicked_function function
      this.$root.$on('partyButtonClicked', this.clicked_function);
  },
};
</script>

<style scoped>
</style>