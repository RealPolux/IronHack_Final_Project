<script setup>
import { onMounted } from "vue";
import CreateNote from "../components/CreateNote.vue";
import Headercomponent from "../components/headercomponent.vue";
import NoteCard from "../components/NoteCard.vue";
import { useNoteStore } from "../stores/note";

const noteStore = useNoteStore();

onMounted(async () => {
  await noteStore.getNotes();
})
</script>

<template>
  <section id="notes-page">
    <h2 class="title">Notes</h2>

    <h3 v-if="noteStore.loading">Notes are loading...</h3>
    <h3 v-else-if="noteStore.error">Oh no! Something went wrong!</h3>
    <ul class="note-list">
      <li><CreateNote /></li>
      <li v-for="note in noteStore.notes" :key="note.id">
        <NoteCard :note="note"></NoteCard>
      </li>
      <li v-if="!noteStore.notes.length" class="empty-msg"><h2>Write your first note</h2></li>
    </ul>
  </section>
</template>

<style>
#notes-page {
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 100vh;
}

.title {
  margin-bottom: 1.5rem;
  text-align: center;
  font-size: 2rem;
  font-weight: bold;
  color: #333;
}

.note-list {
  background-image: url("/assets/fondo2.jpg");
  background-size: cover;
  background-position: top;
  border: 10px solid #1a697d;
  width: 90%;
  min-width: auto;
  padding: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-color: rgb(221, 233, 152);
}

.empty-msg {
  background-color: rgba(255, 255, 255, 0.85);
  border: 2px dashed #7f7044;         
  color: #4a3b1a;                     
  text-align: center;
  font-size: 22px;
  font-weight: 500;
  font-family: 'Poppins', sans-serif;
  padding: 40px 20px;
  border-radius: 12px;
  width: 80%;
  max-width: 600px;
  margin-top: 30px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  transition: all 0.3s ease;
}

.empty-msg:hover {
  background-color: #fffbe6;          
  transform: scale(1.02);
}
</style>
