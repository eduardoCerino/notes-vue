<template>
  <div class="list-group-item">
    <h3>{{ note.title }}</h3>
    <p>{{ note.author }}</p>
    <p>{{ note.datetime }}</p>
    <p>{{ note.body }}</p>
    <p>{{ note.classification }}</p>
  </div>
</template>

<script>
export default {
  props: ['note'],
};
</script>
