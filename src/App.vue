<template>
  <div class="page-container">
    <div class="nav-container">
      <NavBar />
    </div>
    <div class="content-container">
      <router-view />
    </div>
    <div class="extras-container">
      <ExtrasComponent />
    </div>
  </div>
</template>

<script setup lang="ts">
  import NavBar from './components/NavBar.vue'
  import ExtrasComponent from './components/ExtrasComponent.vue';
</script>

<style scoped>
  .page-container {
    display: flex;
    width: 100%;
  }

  .nav-container {
    border-right: 1px solid #ccc;
    width: 20%;
    height: 100vh;
  }

  .content-container {
    width: 60%;
  }

  .extras-container {
    border-left: 1px solid #ccc;
    width: 20%;
    height: 100vh;
  }
</style>
