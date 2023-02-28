<template>
  <div id = "note-frame"
       v-on:click="clickCbk"
       class = "none"
       :class = "{
           'floating_note': active,
         }"
       ref="root">

    <h2>{{title}}</h2>
    <slot/>
  </div>
</template>

<style scope>
#note-frame {
  background-color: #865DFF;
  color: white;

  width: 200px; height: auto;
  overflow: hidden;
  position: absolute;

  border-radius: 10px;
  margin:10px;
  padding:10px;
  cursor: pointer;
  display: flex;
  flex: 0;
  flex-direction: column;
  transition: top 0.5s ease, left 0.5s ease;
}

.none {
  transition: 

}
.floating_note {
  top: calc(10% + 60px);
  left: 10%;
  width: 80% !important ;
  height: 80% !important ;
}

h2 {
  font-weight: 700;
}

.v-enter-active, .v-leave-active {
/*    transition: opacity 0.5s ease; */
  }

.v-enter-from, .v-leave-to {
/*    opacity: 0; */
  }
</style>

<script lang = 'ts'>
import { defineComponent } from 'vue';
export default defineComponent({
  props: {
    title: String,
    note: String
  },
  data() {
    return {
      active: false,
      showText: false
    }
  },
  methods : {
    transitionEnd() {
      this.$refs.root.removeEventListener("transitionend", this.transitionEnd);
    },

    clickCbk() { 
      this.active = !this.active;
    }
  }
});
</script>

