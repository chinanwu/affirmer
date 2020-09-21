<template>
  <div class="DropdownContainer" aria-labelledby="dropdownLabel">
    <span id="dropdownLabel" class="Dropdown__label">AFFIRM ME ABOUT:</span>
    <div class="Dropdown">
      <ul
        :class="{ Dropdown__content: true, ' Dropdown__content--open': isOpen }"
        @mouseleave="isOpen = false"
      >
        <li
          class="Dropdown__option"
          v-for="(option, index) in getAvailableOptions()"
          :key="'dropdown-' + index"
        >
          <button class="Dropdown__optionBtn" @click="onClick(option)">
            {{ option }}
          </button>
        </li>
      </ul>
      <button @click="isOpen = !isOpen">{{ selected }}</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Dropdown",
  data() {
    return {
      options: ["Anything", "Work", "Love", "Body", "Life"],
      isOpen: false,
      selected: "Anything",
    };
  },
  methods: {
    getAvailableOptions() {
      return this.options.filter((item) => item !== this.selected);
    },
    onClick(option) {
      this.selected = option;
      this.isOpen = false;
      this.$emit("on-selected-change", this.selected);
    },
  },
  emits: ["on-selected-change"],
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
  width: 9rem;
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
  max-height: 50rem;
}

.Dropdown__optionBtn {
  font-size: 1.6rem;
  padding: 1rem;
  background-color: white;
  cursor: pointer;
  width: 100%;
}

.Dropdown__optionBtn:focus,
.Dropdown__optionBtn:hover {
  background-color: #efeeee;
}

.Dropdown__optionBtn:focus {
  background-color: #efeeee;
}
</style>
