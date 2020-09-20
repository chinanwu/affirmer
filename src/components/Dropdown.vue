<template>
  <div class="DropdownContainer" aria-labelledby="dropdownLabel">
    <span id="dropdownLabel" class="Dropdown__label">AFFIRM ME ABOUT:</span>
    <div class="Dropdown">
      <ul
        :class="{ Dropdown__content: true, ' Dropdown__content--open': isOpen }"
      >
        <li v-for="(option, index) in options" :key="'dropdown-' + index">
          {{ option }}
        </li>
      </ul>
      <button @click="isOpen = !isOpen">Anything</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Dropdown",
  data() {
    return {
      options: ["Work", "Love"],
      isOpen: false,
    };
  },
};
</script>

<style scoped>
.DropdownContainer {
  display: flex;
  align-items: center;
  margin-bottom: 2rem;
}

.Dropdown__label {
  letter-spacing: 0.3rem;
}

.Dropdown__label::after {
  content: "\00a0";
}

.Dropdown {
  position: relative;
}

button {
  background: white;
  border: none;
  font-size: 1.6rem;
  cursor: pointer;
  padding: 1rem;
}

.Dropdown__content {
  position: absolute;
  bottom: 2.4rem;
  list-style: none;
  text-align: center;
  padding: 0;
  width: 100%;
  max-height: 0;
  transition: max-height 0.2s;
  overflow: hidden;
}

.Dropdown__content--open {
  max-height: 10rem;
}

li {
  font-size: 1.6rem;
  padding: 1rem;
  background-color: white;
}
</style>
