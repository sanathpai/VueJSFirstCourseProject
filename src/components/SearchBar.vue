<template>
  <div>
    <input @input="onInput" />
    <!-- @input is same as v-on:input-->
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onInput: function(event) {
      this.$emit("termChange", event.target.value); //child to parent communication is event while vice versa is prop
    }
  }
};
</script>


<style>
</style>