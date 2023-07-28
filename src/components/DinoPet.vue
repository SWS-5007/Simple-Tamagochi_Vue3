<script>
import { defineAsyncComponent } from "vue";

export default {
  components: {
    DinoAngry: defineAsyncComponent(() => import("./DinoAngry")),
    DinoHappy: defineAsyncComponent(() => import("./DinoHappy")),
    DinoSleep: defineAsyncComponent(() => import("./DinoSleep"))
  },
  props: {
    mood: {
      type: String,
      default: "Angry"
    }
  },
  computed: {
    dinoMood() {
      return `Dino${this.mood}`;
    }
  }
};
</script>

<template>
  <component :is="dinoMood" />
</template>

<style></style>
