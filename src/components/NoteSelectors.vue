<script>
import NoteSelector from "./NoteSelector.vue";

export default {
  components: {
    NoteSelector,
  },
  data: function () {
    return {
      notes: [
        { id: 1, body: "this is a test", timestamp: Date.now() },
        { id: 2, body: "this is the second test", timestamp: Date.now() },
        { id: 3, body: "this is the third test", timestamp: Date.now() },
        { id: 4, body: "this is the fourth test", timestamp: Date.now() },
      ],
    };
  },
};
</script>

<template>
  <div class="note-selectors">
    <NoteSelector v-for="note in notes" v-bind:note="note" v-bind:key="note.id" />
  </div>
</template>
