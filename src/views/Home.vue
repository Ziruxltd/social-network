<template>
  <div class="home-container">
    <nav>
      <ul>
        <li><button :class="{ active: activeTab === 'discover' }" type="button" @click="activeTab = 'discover'">Discover</button></li>
        <li><button :class="{ active: activeTab === 'following' }" type="button" @click="activeTab = 'following'">Following</button></li>
      </ul>
    </nav>
    <div>
      <h1>Welcome to my social network</h1>
      <p>This is just a sample text. If you read it you are more intelligent.</p>
      <div class="posts-container">
        <div v-if="activeTab === 'discover'">
          <!-- Content for Discover tab -->
          1
        </div>
        <div v-else>
          <!-- Content for Following tab -->
          2
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 'discover'
    };
  }
};
</script>

<style scoped>
.home-container {
  width: 100%; /* Ensure the container takes the full width */
  height: 100%; /* Ensure the container takes the full height */
}
nav {
  border-bottom: 1px solid #ccc;
}

ul {
  margin: 0;
  padding: 0;
  display: flex;
}

li {
  width: 50%;
}

button {
  width: 100%;
  padding: 1rem;
  background-color: white;
  border: none;
  cursor: pointer;
  border-radius: 0;
  color: #42576C;
}

button:hover {
  background-color: #e1e1e1;
}

button.active {
  font-weight: bold;
}

.active {
  color: Black;
  position: relative;
}

.active::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 15%;
  width: 70%;
  height: 2px;
  background-color: #1083fe;
}
</style>