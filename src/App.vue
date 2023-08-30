<template>
  <div class="container">
    <textarea :value="input" @input="onInputChange" @keyup="onPress">
    </textarea>
    <SimpleKeyboard @onChange="onChange" @onKeyPress="onKeyPress" :status="status" :input="input"/>
  </div>
</template>

<script>
import SimpleKeyboard from "./SimpleKeyboard";
import "./App.css";

export default {
  name: "App",
  components: {
    SimpleKeyboard
  },
  data: () => ({
    input: "",
    status: ""
  }),
  methods: {
    onChange(input) {
      this.input = input;
    },
    onKeyPress(button) {
      console.log("button", button);
    },
    onPress(e) {
      this.status = e.key
    },
    onInputChange(input) {
      this.input = input.target.value;
    }
  }
};
</script>
