<template>
  <form @submit.prevent="submitForm">
    <basic-text-field
      v-for="field in fields"
      :key="field.id"
      :type="field.type"
      :placeholder="field.placeholder"
      :textFieldClass="field.textFieldClass"
      :isInvalid="field.isInvalid"
    ></basic-text-field>
    <basic-button
      v-for="button in buttons"
      :buttonClass="button.buttonClass"
      :type="button.type"
      :key="button.id"
      >{{ button.text }}</basic-button
    >
  </form>
</template>

<script>
import BasicTextField from "./BasicTextField";
import BasicButton from "./BasicButton";
export default {
  props: {
    fields: {
      type: Array,
      default: null,
    },
    buttons: {
      type: Array,
      default: null,
    },
  },
  components: {
    BasicTextField,
    BasicButton,
  },
  methods: {
    submitForm(data) {
      //TODO validate fields before emitting event
      this.$emit("formSubmitted", data);
    },
  },
};
</script>
