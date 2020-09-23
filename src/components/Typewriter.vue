<template>
  <div class="Typewriter">
    <span class="Typewriter__message">{{ typed }}</span>
    <span class="Typewriter__cursor">|</span>
  </div>
</template>

<script>
export default {
  name: "Typewriter",
  props: {
    message: String
  },
  data() {
    return {
      typed: this.message[0]
    };
  },
  methods: {
    typeMessage() {
      setInterval(() => {
        if (this.typed != this.message) {
          this.typed = this.typed + this.message[this.typed.length];
        }
      }, 100);
    }
  },
  mounted() {
    this.typeMessage();
  }
};
</script>

<style lang="less" scoped>
.Typewriter {
  font-size: 3rem;
  text-align: center;
  padding: 2rem;
}

.Typewriter__message {
  letter-spacing: 0.1rem;
}

.Typewriter__cursor {
  animation: blink 0.8s infinite;
}

@keyframes blink {
  0% {
    color: transparent;
  }
  50% {
    color: black;
  }
  100% {
    color: transparent;
  }
}

.list-item {
  display: inline-block;
  margin-right: 10px;
}
.list-enter-active,
.list-leave-active {
  transition: all 1s ease;
}
.list-enter-from,
.list-leave-to {
  opacity: 0;
  transform: translateY(30px);
}
</style>