<script setup></script>

<template>
  <header class="header">
    <h1 class="title">Notes Page</h1>
    <nav>
      <ul class="nav-list">
        <li>
          <Router-link to="/" class="link">Home</Router-link>
        </li>
        <li>
          <Router-link to="notes" class="link">Notes</Router-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style>
.header {
  background-color: #7f7044;
  color: white;
  padding: 30px;
  text-align: center;

  .header.title {
    margin: 0;
    font-size: 2rem;
    font-weight: bold;
  }

  .nav-list {
    margin: 25px 0 0;
  display: flex;
  justify-content: center;
  gap: 80px;
  list-style: none;
  padding: 0;
  }
  
}
</style>
