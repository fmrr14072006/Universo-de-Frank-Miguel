<script setup>
import { ref } from 'vue';
import Card from "../components/Card.vue"

let character = ref([])


async function loadCharacters(){
  const response = await fetch('http://fmrruapi.com/api/character?page=1')
  const data = await response.json()
  charactervaleu = data.results
  console.log(data)
}
loadCharacters()
</script>

<template>
  <div class="flex justify-center mt-10">
    <h1 class="text-5xl">Personajes del Universo de Frank Miguel </h1>
  </div>

  <div v-for="personaje in character" ::key="character.id">
  {{ personaje.name }}
  </div>

  <!--Card :chracter="character"/> -->
</template>
