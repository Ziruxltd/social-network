<template>
  <ul>
    <RouterLink class="nav-link" v-for="route in routes" :key="route.path" :to="route.path" @click="activeRoute = route.path">
      <li :class="{ active: activeRoute === route.path }">
        <span class="material-symbols-outlined">{{ route.icon }}</span> {{ route.name }}
      </li>
    </RouterLink>
  </ul>
</template>

<script setup lang="ts">
import { RouterLink } from 'vue-router';
import { ref, onMounted } from 'vue';
import { useRoute } from 'vue-router';

onMounted(() => {
  activeRoute.value = useRoute().path.split('/')[1] ? `/${useRoute().path.split('/')[1]}` : '/';
})

const activeRoute = ref('/');
const routes = [
  { path: '/', name: 'Home', icon: 'home' },
  { path: '/search', name: 'Search', icon: 'search' },
  { path: '/notifications', name: 'Notifications', icon: 'notifications' },
  { path: '/chat', name: 'Chat', icon: 'chat' },
  { path: '/feeds', name: 'Feeds', icon: 'rss_feed' },
  { path: '/profile', name: 'Profile', icon: 'person' },
  { path: '/settings', name: 'Settings', icon: 'settings' }
];
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
  font-size: 28px;
}

.nav-text {
  font-size: 24px;
}

nav {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  padding: 0 10px;
}

.nav-link {
  text-decoration: none;
  color: inherit;
  display: flex;
  align-items: center;
  margin-bottom: 8px;
  justify-content: end;
}

ul {
  list-style-type: none;
  padding: 0;
  display: flex;
  flex-direction: column;
}

li {
  width: 60%;
  display: flex;
  padding: 10px;
  border-radius: 10px;
}

li:hover {
  background-color: #f1f1f1;
  cursor: pointer;
}

li.active {
  color: black;
  position: relative;
}

li.active a {
  font-weight: 700;
}

nav a {
  text-decoration: none;
  color: inherit;
  display: flex;
  align-items: center;
}

.active {
  font-weight: 900;
}
</style>