<template>
  <button
    class="basic-button-gi"
    :class="buttonClass"
    :type="type"
    @click="buttonClicked"
  >
    <slot></slot>
    <div v-if="isLoading">LOADER</div>
  </button>
</template>

<script>
export default {
  props: {
    buttonClass: {
      type: String,
      default: "",
    },
    isLoading: {
      type: Boolean,
      default: false,
    },
    type: {
      type: String,
      default: "button",
    },
  },
  methods: {
    buttonClicked() {
      this.$emit("buttonClicked");
    },
  },
};
</script>

<style lang="scss">
.basic-button-gi {
  border: none;
  border-radius: 100px;
  background-color: #18c746;
  color: #fff;
  font-size: 1.6rem;
  line-height: 2rem;
  cursor: pointer;
}
</style>
