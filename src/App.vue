<script setup lang="ts">
import NavBar from './components/NavBar.vue';
import NoteFrame from './components/NoteFrame.vue';
</script>

<template>
  <NavBar/>
  <div id = "note-holder">
    <NoteFrame title = "I am safe in my box">I'm smol</NoteFrame>
    <NoteFrame title = "I am safe in my box">I'm smol too</NoteFrame>
    <NoteFrame title = "I am so far beyond you">
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
  </div>
</template>

<style scoped>
html, body {
    height: 100%;
  }

h2 {
  font-weight: 700;
}

#note-holder {
  display:flex;
  position:relative;
}
</style>
