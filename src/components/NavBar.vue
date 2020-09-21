<template>
  <div>
    <button>WHAT</button>
    <button>WHY</button>
  </div>
</template>

<script></script>

<style scoped>
div {
  position: absolute;
  top: 0;
  width: 100%;
  display: flex;
  justify-content: end;
}

button {
  background-color: inherit;
  padding: 1rem;
  margin-right: 1rem;
  font-size: 1.8rem;
  box-shadow: rgba(255, 255, 255, 0.3) 0px -0.5rem 0px inset;
  transition: box-shadow 0.2s;
  letter-spacing: 0.3rem;
}

button:hover,
button:focus {
  box-shadow: white 0px -3rem 0px inset;
}
</style>
