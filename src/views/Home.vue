<script>
import { reactive, toRefs } from "vue";
import GigaVue from "@/components/GigaVue.vue";
import ProgressBar from '@/components/ProgressBar.vue';

export default {
  name: "Home",

  components: {
    GigaVue,
    ProgressBar
  },

  setup() {
    const state = reactive({
      petName: "",
      petMood: "Happy",
      userInput: "",
      showCreatePetForm: true,
      progress: 0,
    });

    const createPet = () => {
      state.petName = state.userInput;
      state.showCreatePetForm = false;
    };

    const updatePetMood = mood => {
      state.petMood = mood;

      state.progress += 10;
      if (state.progress > 100) {
        state.progress = 100;
      }
    };

    return {
      ...toRefs(state),
      createPet,
      updatePetMood
    };
  },
};
</script>

<template>
  <div class="home">
    <h1>Tamagochi-Vue</h1>

    <section>
      <GigaVue :petName="petName" :petMood="petMood" />
    </section>

    <h2>{{ petName }}</h2>

    <form v-if="showCreatePetForm" @submit.prevent>
      <label for="pet-name">Pet Name</label>
      <input type="text" id="pet-name" v-model="userInput" />
      <button @click="createPet">New Pet</button>
    </form>

    <div v-else class="button_div">
      <button @click="updatePetMood('Happy')">Train</button>
      <button @click="updatePetMood('Angry')">Play</button>
      <button @click="updatePetMood('Sleep')">Sleep</button>
    </div>

    <section>
      <progress-bar :progress="progress"></progress-bar>
    </section>
  </div>
</template>

<style>
.button_div {
  display: flex;
  justify-content: center;
  gap: 20px;
}
</style>
