<script setup>
import Headercomponent from '../components/headercomponent.vue';

</script>

<template>
  <section class="home-page">
    <h1 class="home-title">Welcome to Notes App</h1>
    <p class="home-msg">Go to the <span class="highlight">Notes</span> page to start 📝</p>
  </section>
</template>

<style>
.home-page {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 80vh;
  background-color: #fffef5;
  text-align: center;
  padding: 40px;
}

.home-title {
  font-size: 40px;
  color: #4a3b1a;
  margin-bottom: 20px;
  font-family: 'Poppins', sans-serif;
}

.home-msg {
  font-size: 22px;
  color: #6b5a2a;
  background-color: #f7efc5;
  padding: 20px 30px;
  border-radius: 12px;
  border: 2px solid #c7b37a;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  font-family: 'Poppins', sans-serif;
}

.highlight {
  color: #7f7044;
  font-weight: 600;
}
</style>