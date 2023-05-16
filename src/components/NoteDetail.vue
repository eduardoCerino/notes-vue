<template>
  <div>
    <h2>Note Detail</h2>
    <div v-if="note">
      <h3>{{ note.title }}</h3>
      <p>{{ note.author }}</p>
      <p>{{ note.datetime }}</p>
      <p>{{ note.body }}</p>
      <p>{{ note.classification }}</p>
      <button @click="editNote" class="btn btn-primary">Edit</button>
      <button @click="deleteNote">Delete</button>

    </div>
    <div v-else>
      <p>Loading...</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      note: null,
    };
  },
  created() {
    // Fetch the note details from the API when the component is created
    this.fetchNote();
  },
  methods: {
    fetchNote() {
      // Use an HTTP library (e.g., Axios) to make a GET request to the API endpoint with the note ID and update the note object
    },
    editNote() {
      // Redirect to the note edit page or emit an event to notify the parent component about the request to edit the note
    },
  },
};
</script>
