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
      selectedNoteId: 1,
    };
  },
  methods: {
    selectNote: function (note) {
      this.selectedNoteId = note.id;
    },
  },
};
</script>

<template>
  <div class="note-selectors">
    <NoteSelector
      v-for="note in notes"
      v-bind:note="note"
      v-bind:selectedNoteId="selectedNoteId"
      v-on:selectNote="selectNote(note)"
      v-bind:key="note.id"
    />
  </div>
</template>
