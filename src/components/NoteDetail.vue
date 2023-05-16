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
    this.fetchNote();
  },
  methods: {
    fetchNote() {
    },
    editNote() {
    },
  },
};
</script>
