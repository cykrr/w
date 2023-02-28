<script setup lang="ts">
import NavBar from './components/NavBar.vue';
import NoteFrame from './components/NoteFrame.vue';
</script>

<template>
  <NavBar/>

  <NoteFrame title = "I am safe in my box">I'm smol</NoteFrame>
  <NoteFrame title = "I am far beyond you">
    I am
    <br>
    the largest
    <br>
    note
    <br>
    in this universe
    <br>
    also the skinnier
    <br>
    one.
  </NoteFrame>
</template>

<style scoped>
#app, body {
    padding-top: 40px;
    width: 100%;
  }

</style>
