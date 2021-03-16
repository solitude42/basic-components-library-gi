<template>
  <div id="app">
    <basic-text-field placeholder="email" :isInvalid="true"></basic-text-field>
    <basic-button @buttonClicked="onClick" :isLoading="isButtonLoading"
      >click button</basic-button
    >
    <basic-button button-class="inverted-button">click button</basic-button>
    <basic-form
      @formSubmitted="printForm"
      :fields="formFields"
      :buttons="formButtons"
    ></basic-form>
    <basic-loader></basic-loader>
  </div>
</template>

<script>
import BasicButton from "./components/BasicButton";
import BasicTextField from "./components/BasicTextField";
import BasicLoader from "./components/BasicLoader";
import BasicForm from "./components/BasicForm";
export default {
  name: "App",
  components: {
    BasicButton,
    BasicTextField,
    BasicLoader,
    BasicForm,
  },
  data() {
    return {
      isButtonLoading: false,
      formFields: [
        {
          id: "email",
          type: "email",
          placeholder: "e-mail*",
        },
        {
          id: "password",
          type: "password",
          placeholder: "password*",
        },
      ],
      formButtons: [
        {
          id: "submit",
          type: "submit",
          text: "Submit",
        },
        {
          id: "googleLogin",
          buttonClass: "inverted-button",
          text: "Google",
        },
      ],
    };
  },
  methods: {
    onClick() {
      this.isButtonLoading = true;
      setTimeout(() => {
        this.isButtonLoading = false;
      }, 2000);
    },
    printForm(data) {
      console.log(data);
    },
  },
};
</script>

<style lang="scss">
html {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 62.5%;
}

.inverted-button {
  background-color: #fff;
  color: #0084f4;
  border: 1px solid #0084f4;
}
</style>
