<script setup>
import { ref as useState } from 'vue';

const showModal = useState(false);
const newNoteDesc = useState('');
const notes = useState([]);

const toggleModal = () => (showModal.value = !showModal.value);

const clearNewNoteDesc = () => (newNoteDesc.value = '');

const addNote = () => {
  if (!newNoteDesc.value) return;

  notes.value.push({ id: Date.now(), desc: newNoteDesc.value });
  clearNewNoteDesc();
};

const formatDate = (timestamp) =>
  new Date(timestamp).toLocaleDateString('ru-RU', {
    weekday: 'short',
    year: 'numeric',
    month: 'long',
    day: 'numeric',
  });
</script>

<template>
  <section class="notepad">
    <div :class="`overlay ${showModal ? '' : 'visually-hidden'}`">
      <form class="modal" @submit.prevent="addNote" @click="toggleModal">
        <textarea
          name="desc"
          cols="50"
          rows="10"
          minlength="10"
          placeholder="Введите описание заметки (минимум 10 символов)"
          @click.stop
          v-model.lazy.trim="newNoteDesc"
        ></textarea>
        <button type="submit" class="btn-save">save</button>
      </form>
    </div>
    <h2 class="notepad__header">Notes</h2>
    <button type="button" class="btn-add-new" @click.prevent="toggleModal">+</button>
    <ul class="notepad__list">
      <li class="note" v-for="note of notes" :key="note.id">
        <span class="note__desc">{{ note.desc }}</span>
        <span class="note__date"> {{ formatDate(note.id) }}</span>
      </li>
    </ul>
  </section>
</template>

<style>
.notepad {
  position: relative;
  max-width: 80vw;
  min-height: 80vh;
  margin: 0 auto;
  box-sizing: border-box;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  background-color: rgb(207, 197, 197);
}

.overlay {
  position: absolute;
  z-index: 10;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.77);
}

.modal {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1rem;
}

.notepad__header {
  text-align: center;
  margin: 0;
  padding: 0.5rem;
}

.notepad__list {
  list-style: none;
  margin: 1rem;
  margin-top: 2rem;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1rem;
}

.note {
  padding: 1rem;
  min-width: 80%;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(2, 1fr);
  gap: 1rem;

  background-color: goldenrod;
}

.note__date {
  font-size: 0.7rem;
  font-weight: 700;
}

button {
  border: none;
  padding: 0.5rem;

  display: flex;
  align-items: center;
  justify-content: center;

  background-color: black;
  color: goldenrod;

  font-size: 2rem;
}

.btn-add-new {
  width: 3rem;
  height: 3rem;
  position: absolute;
  top: 0.5rem;
  right: 0.5rem;
}

.btn-save {
  color: black;
  background-color: goldenrod;
}

.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  border: 0;
  padding: 0;
  white-space: nowrap;
  clip-path: inset(100%);
  clip: rect(0 0 0 0);
  overflow: hidden;
}
</style>
