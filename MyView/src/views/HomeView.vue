<script setup lang="ts">
import { reactive, ref } from 'vue';
const firstname = ref('pierre');
let isMale = ref(true);

let sampleUser = reactive({
  username: 'pierre',
  birthdate: {
    year: 2022,
    month: 12,
    day: 7
  }
})

function changeGender(): void {
  console.log("here");
  isMale.value = !isMale.value;
}
</script>

<template>
  <main>
    <div v-if="isMale">
      bonjour Monsieur
    </div>
    <div v-else>
      bonjour Madame
    </div>
    {{firstname}}

    <button @click="$event => changeGender()">Change gender</button>
  </main>
</template>
