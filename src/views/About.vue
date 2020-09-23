<template>
  <div class="About">
    <h1 class="About__header">Affirmations</h1>

    <article>
      <h2>What?</h2>
      <p>Affirmations are.... blah blah blah bloop</p>
    </article>

    <article>
      <h2>Why?</h2>
      <p>Affirmations are great! blah etc go on</p>
    </article>

    <article>
      <h2>Who are you?</h2>
      <p>Hi! I'm Salmon, I'm a software developer located on Tkaronto.</p>
    </article>

    <article>
      <h2>How can I support this site?</h2>
      <p>Buy me a ko-fi!</p>
    </article>

    <router-link to="/">
      <button>HOME</button>
    </router-link>
  </div>
</template>

<script>
export default {
  name: "About"
};
</script>

<style lang="less">
.About__header {
  text-align: center;
}
</style>
