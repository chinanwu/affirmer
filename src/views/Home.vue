<template>
  <transition name="fade" mode="out-in">
    <div v-if="isHome" class="Home">
      <div class="Home__main">
        <h1 class="Home__header">Affirm me about:</h1>

        <div class="Home__btns">
          <Button
            label="Life"
            colourClass="Button__life"
            @on-click="handleClick"
          />
          <Button
            label="Work"
            colourClass="Button__work"
            @on-click="handleClick"
          />
          <Button
            label="Body"
            colourClass="Button__body"
            @on-click="handleClick"
          />
          <Button
            label="Love"
            colourClass="Button__love"
            @on-click="handleClick"
          />
        </div>
        <Button
          label="Anything"
          colourClass="Button__anything"
          @on-click="handleClick"
        />
      </div>
    </div>
    <div v-else>
      <h1 class="Home__header">Repeat after me...</h1>
      <Typewriter :message="affirmation" />
    </div>
  </transition>
  <transition name="fade" mode="out-in">
    <div v-if="isHome" class="Home__about">
      <router-link to="/about">
        <button class="Home__aboutBtn">ABOUT</button>
      </router-link>
    </div>
    <div v-else class="Home__return">
      <button class="Home__returnBtn" @click="clearAffirmation">Return</button>
    </div>
  </transition>
</template>

<script>
// @ is an alias to /src
import { affirmations } from "@/assets/affirmations.js";
import Button from "@/components/Button.vue";
import Typewriter from "@/components/Typewriter.vue";

export default {
  name: "Home",
  data() {
    return {
      isHome: true,
      affirmation: ""
    };
  },
  components: {
    Button,
    Typewriter
  },
  methods: {
    handleClick(affirmationCategory) {
      this.isHome = false;
      let category = null;
      if (affirmationCategory === "Anything") {
        const categoriesLen = affirmations.length;
        category =
          affirmations[Math.round(Math.random() * (categoriesLen - 1))];
      } else {
        for (let i = 0; i < affirmations.length; i++) {
          if (affirmations[i].category === affirmationCategory) {
            category = affirmations[i];
            break;
          }
        }
      }

      const len = category.list.length;
      this.affirmation = category.list[Math.round(Math.random() * (len - 1))];
    },
    clearAffirmation() {
      this.isHome = true;
      this.affirmation = "";
    }
  }
};
</script>

<style lang="less">
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.7s ease, transform 0.7s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-100%);
}

.fade-enter-to,
.fade-leave-from {
  opacity: 1;
  transform: translateY(0);
}

.Home {
  min-height: 100%;
}

.Home__main {
  padding: 1rem 1.6rem;
}

.Home__header {
  text-align: center;
  text-decoration: underline;
}

.Home__btns {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
  grid-gap: 2.4rem;
  justify-items: center;
}

.Home__about,
.Home__return {
  position: absolute;
  bottom: 1rem;
  width: 100%;
  display: flex;
  justify-content: center;
}

.Home__aboutBtn {
  background-color: inherit;
  border: none;
  font-size: 1.6rem;
  box-shadow: rgba(0, 0, 0, 0.3) 0px -0.5rem 0px inset;
  transition: box-shadow 0.2s;
  cursor: pointer;
  padding: 0.5rem;

  &:focus,
  &:hover {
    box-shadow: rgb(253, 228, 131) 0px -4rem 0px inset;
  }

  &:active {
    box-shadow: rgb(253, 228, 131) 0px -4rem 0px inset,
      0 0 0 0.4rem rgba(245, 230, 149, 0.4);
  }
}

.Home__returnBtn {
  background-color: inherit;
  font-size: 1.6rem;
  cursor: pointer;
  border: 1px solid #dedede;
  border-radius: 1rem;
  padding: 1rem 3rem;
  transition: box-shadow 0.2s;

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

<!-- 
TODO
- About button may be a footer 
- Letter spacing
- Line height
- Secondary transition for About? Maybe google transition for absolute positioned elements
-->
