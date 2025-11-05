<script setup>
import { ref } from "vue";
import { useNoteStore } from "../stores/note";

const noteStore = useNoteStore();

const title = ref("");

const handleSubmit = () => {
  noteStore.addNote(title.value);
  title.value = '';
};
</script>

<template>
  <form class="note-form" @submit.prevent="handleSubmit">
    <input
      type="text"
      class="note-title"
      placeholder="New Note"
      v-model="title"
    />
    <button type="submit" class="create-btn">+</button>
  </form>
</template>

<style>
.note-form {
  width: 600px;
  background-color: #fffef5;
  border: 2px solid #c7b37a;
  padding: 20px;
  margin-bottom: 30px;
  display: flex;
  justify-content: center;
  gap: 12px;
  transition: all 0.3s ease;
}

.note-title {
  flex: 1;
  min-width: 0;
  background-color: #ffffff;
  border: 2px solid #b19024;
  font-size: 18px;
  font-weight: 500;
  padding: 10px 12px;
  border-radius: 8px;
  color: #333;
  outline: none;
}

.create-btn {
  width: 140px;
  height: 40px;
  font-size: 16px;
  background-color: #7f7044; /* marrón del header */
  color: #ffffff;
  display: flex;
  align-items: center;      /* <- faltaba el valor */
  justify-content: center;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.create-btn:hover {
  background-color: #a08b55;
}

.create-btn:active {
  background-color: #5f5132;
}

.note-form:hover {
  border: 2px solid #a68c47;
  box-shadow: 0px 4px 12px rgba(0, 0, 0, 0.15);
}
</style>