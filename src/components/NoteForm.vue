<template>
  <div class="mt-5">
    <h2>Add Note ➕</h2>
    <form @submit.prevent="submitForm" class="needs-validation">
      <div class="mb-3">
        <label for="title" class="form-label">Title:</label>
        <input type="text" v-model="note.title" class="form-control" required />
      </div>

      <div class="mb-3">
        <label for="author" class="form-label">Author:</label>
        <input
          type="text"
          v-model="note.author"
          class="form-control"
          required
        />
      </div>

      <div class="mb-3">
        <label for="datetime" class="form-label">Date and Time:</label>
        <input
          type="datetime-local"
          v-model="note.datetime"
          class="form-control"
          required
        />
      </div>

      <div class="mb-3">
        <label for="body" class="form-label">Body:</label>
        <textarea v-model="note.body" class="form-control" required></textarea>
      </div>

      <div class="mb-3">
        <label for="classification" class="form-label">Classification:</label>
        <input
          type="text"
          v-model="note.classification"
          class="form-control"
          required
        />
      </div>

      <button type="submit" class="btn btn-primary">Save Note</button>
    </form>
  </div>
</template>

<script>

import axios from 'axios';

export default {
  data() {
    return {
      note: {
        title: '',
        author: '',
        datetime: '',
        body: '',
        classification: '',
      },
    };
  },
  methods: {
    submitForm() {
      axios.post('http://localhost:3000/notes', this.note)
        .then(response => {
          console.log('Note added:', response.data);
        })
        .catch(error => {
          console.error('Error adding note:', error);
        });
    },
  },
};
</script>
