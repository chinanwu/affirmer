<template>
  <div class="About">
    <h1 class="About__header">Affirmations</h1>

    <article>
      <h2>What?</h2>
      <p>
        "Positive affirmations are statements that are repeated to encourage and
        uplift the person speaking them." -
        <a href="https://blog.mindvalley.com/positive-affirmations/"
          >Mindvalley</a
        >
      </p>
    </article>

    <article>
      <h2>Why?</h2>
      <p>
        "People use affirmations for a variety of purposes. Generally speaking,
        affirmations are used to reprogram the subconscious mind, to encourage
        us to believe certain things about ourselves or about the world and our
        place within it. They are also used to help us create the reality we
        want" -
        <a
          href="https://www.psychologytoday.com/us/blog/smart-relationships/201403/affirmations-the-why-what-how-and-what-if"
          >Kathryn J Lively Ph.D.</a
        >
      </p>
    </article>

    <article>
      <h2>Where did these affirmations come from?</h2>
      <ul>
        <li v-for="(source, index) in sources" :key="'aboutSources-' + index">
          <a :href="source.url">{{ source.name }}</a>
        </li>
      </ul>
    </article>

    <article>
      <h2>Who are you?</h2>
      <p>Hi! I'm Salmon, I'm a software developer located on Tkaronto, ON.</p>
    </article>

    <div class="About__btnContainer">
      <router-link to="/">
        <button class="About__btn">HOME</button>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
  data() {
    return {
      sources: [
        {
          name: "Mindvalley",
          url: "https://blog.mindvalley.com/positive-affirmations/"
        },
        {
          name: "Dr. Carmen Harra, via HuffPost",
          url: "https://blog.mindvalley.com/positive-affirmations/"
        },
        {
          name: "@WeTheUrban on instagram",
          url: "https://www.instagram.com/wetheurban/"
        },
        {
          name: "@TheShineApp on instagram",
          url: "https://www.instagram.com/theshineapp/"
        },
        {
          name: "Develop Good Habits",
          url: "https://www.developgoodhabits.com/positive-affirmations/"
        },
        {
          name: "Motivation Ping",
          url: "https://motivationping.com/affirmations/"
        },
        {
          name: "Catherine Moore, Psychologist, MBA via Positive Psychology",
          url: "https://positivepsychology.com/daily-affirmations/"
        }
      ]
    };
  }
};
</script>

<style lang="less">
.About__header {
  text-align: center;
  text-decoration: underline;
}

.About__btnContainer {
  width: 100%;
  display: flex;
  justify-content: center;
}

.About__btn {
  background-color: inherit;
  font-size: 1.6rem;
  cursor: pointer;
  border: 1px solid #dedede;
  border-radius: 1rem;
  padding: 1rem 3rem;
  transition: box-shadow 0.2s;
  margin-bottom: 1rem;

  &:focus,
  &:hover {
    box-shadow: 0 0 0 0.4rem rgba(233, 233, 231, 0.4);
  }

  &:active {
    box-shadow: none;
    background-color: rgba(233, 233, 231, 0.4);
  }
}
</style>
