<template>
  <button>{{ message ? message : "Affirmation" }}</button>
</template>

<script>
import { prompts } from "../assets/prompts.js";

export default {
  name: "Button",
  // data() {
  //   return {
  //     message: "Give me an affirmation!",
  //   };
  // },
  computed: {
    message: {
      get() {
        const len = prompts.length;
        return prompts[Math.round(Math.random() * len)];
      },
    },
  },
};
</script>

<style scoped>
button {
  border: none;
  background-color: white;
  padding: 2rem;
  font-size: 2rem;
  border-radius: 1rem;
  transition: background-color 0.2s, box-shadow 0.5s, font-size 0.5s;
  cursor: pointer;
}

button:hover,
button:focus {
  box-shadow: 0 0 0 0.8rem rgba(255, 255, 255, 0.5);
}

button:active {
  box-shadow: none;
  background-color: #ffffff70;
}
</style>

// Affirm me about: ...
