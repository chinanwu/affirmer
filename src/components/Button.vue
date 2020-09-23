<template>
  <button :class="colourClass" @click="$emit('on-click', label)">
    {{ label }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    label: String,
    colourClass: String
  }
};
</script>

<style scoped lang="less">
button {
  font-family: "Nunito", sans-serif;
  background-color: none;
  border: none;
  // width: 125px;
  width: 100%;
  height: 104px;
  border-radius: 1.5rem;
  font-size: 2.4rem;
  cursor: pointer;
  transition: box-shadow 0.2s, transform 0.2s;
  display: flex;
  justify-content: center;
  align-items: flex-end;
  padding-bottom: 1rem;

  &:active {
    // Need to figure out a better style for this
    transform: translateY(0.5rem);
  }
}

.Button__life {
  background: rgb(245, 201, 149);
  background: linear-gradient(
    146deg,
    rgba(245, 201, 149, 1) 0%,
    rgba(245, 236, 149, 1) 100%
  );

  &:hover,
  &:focus {
    box-shadow: 0 0 0 0.8rem rgba(245, 230, 149, 0.4);
  }

  &:active {
    box-shadow: 0 0 0 0.5rem rgba(245, 230, 149, 0.4);
  }
}

.Button__work {
  background: rgb(245, 236, 149);
  background: linear-gradient(
    146deg,
    rgba(245, 236, 149, 1) 0%,
    rgba(206, 252, 202, 1) 100%
  );

  &:hover,
  &:focus {
    box-shadow: 0 0 0 0.8rem rgba(225, 244, 177, 0.41);
  }

  &:active {
    box-shadow: 0 0 0 0.5rem rgba(225, 244, 177, 0.41);
  }
}

.Button__body {
  background: rgb(149, 228, 245);
  background: linear-gradient(
    146deg,
    rgba(149, 228, 245, 1) 0%,
    rgba(232, 149, 245, 1) 100%
  );

  &:hover,
  &:focus {
    box-shadow: 0 0 0 0.8rem rgba(165, 213, 245, 0.42);
  }

  &:active {
    box-shadow: 0 0 0 0.5rem rgba(165, 213, 245, 0.42);
  }
}

.Button__love {
  background: rgb(232, 149, 245);
  background: linear-gradient(
    146deg,
    rgba(232, 149, 245, 1) 0%,
    rgba(245, 149, 149, 1) 100%
  );

  &:hover,
  &:focus {
    box-shadow: 0 0 0 0.8rem rgba(235, 149, 223, 0.34);
  }

  &:active {
    box-shadow: 0 0 0 0.5rem rgba(235, 149, 223, 0.34);
  }
}

.Button__anything {
  margin-top: 24px;
  background: rgb(251, 255, 177);
  background: radial-gradient(
    circle,
    rgba(251, 255, 177, 1) 0%,
    rgba(247, 184, 169, 1) 100%
  );

  &:hover,
  &:focus {
    box-shadow: 0 0 0 0.8rem rgba(247, 192, 170, 0.32);
  }

  &:active {
    box-shadow: 0 0 0 0.5rem rgba(247, 192, 170, 0.32);
  }
}
</style>
