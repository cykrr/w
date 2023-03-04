<template>
  <div class="note-wrapper" :style = "wrapperStyle" ref = "wrapper">
  <div id = "note-frame"
       v-on:click="onclick"
       class = "note-frame"
       :class = "{
           'floating-note': active,
         }"
       ref="root">

    <h2>{{title}}</h2>
    <slot/>
  </div>
</div>
</template>

<style scope>

.note-wrapper {
  position: relative;
  width: 150px;
  height: auto;
  margin:10px;


}

.note-frame {
  background-color: #865DFF;
  color: white;
  padding:10px;
  border-radius: 10px;
  cursor: pointer;
  display: flex;
  flex-grow: 1;
  flex-direction: column;
  padding: 10px;

  position:relative;
  top: 0; left: 0; right: auto; bottom: auto;
  width: 150px;
  min-width: 150px;
  max-width: 150px;
  min-height: 100px;

  transition: all 0.5s ease;
}

</style>

<script lang = 'ts'>
import { defineComponent } from 'vue';
import { NAV_SZ, NAV_MARGIN } from '@/constants.js';
export default defineComponent({
  props: {
    title: String,
    note: String
  },
  data() : ComponentData {
    return {
      active: false,
    }
  },
  computed: {
      wrapperStyle() { return {
      }}
    },
  methods : {
    onclick () {
      const el = this.$refs.root;
      const wrapper = this.$refs.wrapper;
      const style = this.$refs.root.style;
      const big = window.matchMedia("(max-width: 1024px)");

      this.active = !this.active; 
      if (this.active) {
        const rect = el.getBoundingClientRect();
        const doc_rect = document.body.getBoundingClientRect();
        style.position = "absolute";
        style.zIndex = "1";

        wrapper.style.width = rect.width + "px";
        wrapper.style.height = rect.height + "px";
        
        if (!big) {
          style.top = (- rect.top + NAV_SZ + NAV_MARGIN*2) + "px";
          style.left = (- rect.left + NAV_MARGIN) + "px";

        }
        else {

          }
        style.minWidth = (doc_rect.width - NAV_MARGIN*2) + "px";
        style.minHeight = (doc_rect.height - NAV_SZ - NAV_MARGIN*4) + "px";
        style.maxHeight = (doc_rect.height - NAV_SZ - NAV_MARGIN*4) + "px";
        style.overflow = "scroll";


      } else {
        style.position = "relative";
        style.top = "0px";
        style.left = "0px";
        style.minWidth = "150px";
        style.maxWidth = "150px";
        style.minHeight = "100px";
        style.zIndex = "0"
        style.overflow = "hidden";

        }


    }
  }
});
</script>

