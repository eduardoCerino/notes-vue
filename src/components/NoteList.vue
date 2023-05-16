<template>
  <div class="mt-5">
    <h2>My Notes: ⬇️</h2>
    <ul class="list-group">
      <li class="list-group-item" v-for="note in notes" :key="note.id">
        <note-item :note="note" />
        <button class="btn btn-danger" @click="deleteNote(note.id)">Delete</button>
        <button class="btn btn-warning m-3">Edit</button>


        
      </li>
    </ul>
  </div>
</template>

<script>
import NoteItem from './NoteItem.vue';
import axios from 'axios';

export default {
  components: {
    NoteItem,
  },
  data() {
    return {
      notes: [],
    };
  },
  created() {
    this.fetchNotes();
  },
  methods: {
    fetchNotes() {
      axios
        .get('http://localhost:3000/notes')
        .then((response) => {
          this.notes = response.data;
        })
        .catch((error) => {
          console.error(error);
        });
    },
    deleteNote(noteId){
      axios
        .delete(`http://localhost:3000/notes/${noteId}`)
        .then((response) => {
          console.log('Note deleted:', response.data);
          this.fetchNotes();
        })
        .catch((error) => {
          console.error(error);
        });

    }

  },
};
</script>
