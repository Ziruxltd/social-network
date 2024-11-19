<template>
  <nav>
    <ul>
      <li :class="{ active: activeRoute === '/' }">
        <RouterLink to="/" @click="activeRoute = '/'">
          <span class="material-symbols-outlined">home</span> Home
        </RouterLink>
      </li>
      <li :class="{ active: activeRoute === '/search' }">
        <RouterLink to="/search" @click="activeRoute = '/search'">
          <span class="material-symbols-outlined">search</span> Search
        </RouterLink>
      </li>
      <li :class="{ active: activeRoute === '/notifications' }">
        <RouterLink to="/notifications" @click="activeRoute = '/notifications'">
          <span class="material-symbols-outlined">notifications</span> Notifications
        </RouterLink>
      </li>
      <li :class="{ active: activeRoute === '/chat' }">
        <RouterLink to="/chat" @click="activeRoute = '/chat'">
          <span class="material-symbols-outlined">chat</span> Chat
        </RouterLink>
      </li>
      <li :class="{ active: activeRoute === '/feeds' }">
        <RouterLink to="/feeds" @click="activeRoute = '/feeds'">
          <span class="material-symbols-outlined">rss_feed</span> Feeds
        </RouterLink>
      </li>
      <li :class="{ active: activeRoute === '/profile' }">
        <RouterLink to="/profile" @click="activeRoute = '/profile'">
          <span class="material-symbols-outlined">person</span> Profile
        </RouterLink>
      </li>
      <li :class="{ active: activeRoute === '/settings' }">
        <RouterLink to="/settings" @click="activeRoute = '/settings'">
          <span class="material-symbols-outlined">settings</span> Settings
        </RouterLink>
      </li>
    </ul>
  </nav>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router';
import { ref, onMounted } from 'vue';
import { useRoute } from 'vue-router';

onMounted(() => {
  activeRoute.value = useRoute().path.split('/')[1] ? `/${useRoute().path.split('/')[1]}` : '/';
})

const activeRoute = ref('/');
</script>

<style scoped>
.material-symbols-outlined {
  font-variation-settings:
    'FILL' 0,
    'wght' 400,
    'GRAD' 0,
    'opsz' 48;
  vertical-align: middle;
  margin-right: 8px;
}

nav {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

nav ul {
  list-style: none;
  padding: 0;
  width: 50%;
}

li.active {
  color: black;
  position: relative;
}

li.active a {
  font-weight: 700;
}

nav li {
  display: flex;
  align-items: center;
  margin-bottom: 8px;
}

nav a {
  text-decoration: none;
  color: inherit;
  display: flex;
  align-items: center;
}
</style>