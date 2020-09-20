<template>
  <NavBar />
  <Dropdown />
  <Button />
</template>

<script>
import Button from "./components/Button.vue";
import NavBar from "./components/NavBar.vue";
import Dropdown from "./components/Dropdown.vue";

export default {
  name: "App",
  components: {
    Button,
    NavBar,
    Dropdown,
  },
};
</script>

<style>
html,
body {
  height: 100%;
  margin: 0;
  font-family: "Open Sans", sans-serif;
}

html {
  font-size: 62.5%;
}

body {
  font-size: 1.4rem;
}

h1 {
  font-size: 2.4rem;
  margin: 0;
  padding: 1rem;
}

h2 {
  font-size: 2rem;
  margin: 0;
  padding: 1rem;
}

h3 {
  font-size: 1.8rem;
  margin: 0;
  padding: 1rem;
}

h4 {
  font-size: 1.6rem;
  margin: 0;
  padding: 1rem;
}

p {
  padding-left: 1rem;
  padding-right: 1rem;
}

#app {
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: rgb(232, 226, 48);
  background: radial-gradient(
    circle,
    rgba(232, 226, 48, 1) 0%,
    rgba(232, 193, 48, 1) 100%
  );
}
</style>
