<template>
  <button @click="grabAffirmation">
    {{ message }}
  </button>
</template>

<script>
import { prompts } from "../assets/prompts.js";
import { affirmations } from "../assets/affirmations.js";

export default {
  name: "Button",
  data() {
    return {
      message: prompts[Math.round(Math.random() * (prompts.length - 1))],
    };
  },
  props: {
    selected: String,
  },
  methods: {
    grabAffirmation() {
      if (this.selected === "Anything") {
        const categoriesLen = affirmations.length;
        const category =
          affirmations[Math.round(Math.random() * (categoriesLen - 1))];
        const len = category.list.length;
        console.log(category.list[Math.round(Math.random() * (len - 1))]);
      } else {
        for (let i = 0; i < affirmations.length; i++) {
          if (affirmations[i].category === this.selected) {
            const len = affirmations[i].list.length;
            console.log(
              affirmations[i].list[Math.round(Math.random() * (len - 1))]
            );
            return;
          }
        }
      }
    },
  },
};
</script>

<style scoped>
button {
  padding: 2rem;
  font-size: 2rem;
  border-radius: 1rem;
  transition: background-color 0.2s, box-shadow 0.5s, font-size 0.5s;
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
