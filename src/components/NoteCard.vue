<script setup>
defineProps ({
    note: Object
})
</script>

<template>
    <article class="note-card">
        <input type="text" class="card-title" v-model="note.title">
        <input type="checkbox" v-model="note.marked">
    </article>
</template>

<style>
.note-card {
    width: 400px;
    background-color: rgb(233, 207, 207);
    border: 3px solid black;
    padding: 20px 30px;
    display: flex;
    justify-content: space-between;
    transition: all 0.2s;
    .card-title {
        background-color: transparent;
        border: none;
        font-size: 1.2rem;
        font-weight: bold;
    }
    [type="checkbox"] {
        transform: scale(2) translateX(-2px);
    }
}
.note-card:hover {
    border: 3px solid black;
    box-shadow: 0 0 10px;
}
.note-card:has(input:checked) {
    border: 3px solid lightcyan;
    background-color: lightcyan;
    .card-title {
        font-weight: 100;
    }
}
</style>