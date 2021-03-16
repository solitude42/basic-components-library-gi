<template>
  <input
    :class="[textFieldClass, { 'input-invalid': isInvalid }]"
    :type="type"
    :placeholder="placeholder"
  />
</template>

<script>
export default {
  props: {
    textFieldClass: {
      type: String,
      default: "",
    },
    isInvalid: {
      type: Boolean,
      default: false,
    },
    type: {
      type: String,
      default: "text",
    },
    placeholder: {
      type: String,
      default: "",
    },
  },
};
</script>

<style lang="scss" scoped>
input {
  color: #23445a;
  border: none;
  border-bottom: 1px solid #23445a;
}

.input-invalid {
  color: red;
  border-bottom-color: red;
}
</style>
