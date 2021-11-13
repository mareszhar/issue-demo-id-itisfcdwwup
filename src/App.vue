<script setup lang="ts">
import { ref } from "vue";
import { Character } from "./types";

const demoMaker = ref<Character>({
  age: 99,
  role: "wizard",
});
</script>

<template lang="pug">
h1 Hi, I am a {{ demoMaker.age }}-year-old {{ demoMaker.role }}
</template>

<style>
body {
  font-family: sans-serif;
  background: hsl(250, 10%, 10%);
  color: whitesmoke;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0;
  padding: 0;
}
</style>
