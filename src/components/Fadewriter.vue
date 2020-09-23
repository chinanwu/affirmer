<template>
  <div class="Fadewriter">
    <transition-group name="list" tag="p">
      <span v-for="item in faded" :key="item" class="list-item">{{ item }}</span>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: "Fadewriter",
  props: {
    message: Array
  },
  data() {
    return {
      faded: []
    };
  },
  methods: {
    fadeMessage() {
      setInterval(() => {
        if (this.faded.length != this.message.length) {
          this.faded.push(this.message[this.faded.length]);
        }
      }, 500);
    }
  },
  mounted() {
    this.fadeMessage();
  }
};
</script>

<style lang="less" scoped>
.Fadewriter {
  font-size: 3rem;
  text-align: center;
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