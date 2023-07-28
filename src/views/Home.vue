<script>
import { reactive, toRefs } from "vue";
import GigaVue from "@/components/GigaVue.vue";

export default {
  name: "Home",
  components: {
    GigaVue
  },
  setup() {
    const state = reactive({
      petName: "",
      petMood: "Happy",
      userInput: "",
      showCreatePetForm: true
    });

    const createPet = () => {
      state.petName = state.userInput;
      state.showCreatePetForm = false;
    };

    const updatePetMood = mood => {
      state.petMood = mood;
    };

    return {
      ...toRefs(state),
      createPet,
      updatePetMood
    };
  }
};
</script>

<template>
  <div class="home">
    <h1>Giga-Vue</h1>
    <section>
      <GigaVue :petName="petName" :petMood="petMood" />
    </section>
    <h2>{{ petName }}</h2>
    <form v-if="showCreatePetForm" @submit.prevent>
      <label for="pet-name">Pet Name</label>
      <input type="text" id="pet-name" v-model="userInput" />
      <button @click="createPet">New Pet</button>
    </form>
    <div v-else>
      <button @click="updatePetMood('Happy')">Happy</button>
      <button @click="updatePetMood('Angry')">Angry</button>
      <button @click="updatePetMood('Sleep')">Sleep</button>
    </div>
  </div>
</template>

<style module></style>
