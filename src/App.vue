<template>
  <div id="app">
    <h1>My Notes App 📝</h1>
    <note-form />
    <note-list />
  </div>
</template>

<script>
import NoteForm from './components/NoteForm.vue';
import NoteList from './components/NoteList.vue';
import 'bootstrap/dist/css/bootstrap.css';
import 'bootstrap';

export default {
  name: 'App',
  components: {
    NoteForm,
    NoteList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 2rem;
}
</style>
