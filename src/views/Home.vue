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
          <PostComponent v-for="post in posts" :key="post.id" :post="post" />
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
import PostComponent from '../components/PostComponent.vue';

export default {
  components: {
    PostComponent
  },
  data() {
    return {
      activeTab: 'discover',
      posts: [
        {
          id: 1,
          user: {
            name: 'John Doe',
            username: 'johndoe',
            profileImage: 'https://via.placeholder.com/50'
          },
          content: 'This is a mock post content 1 lore ipsum y muchas cosas mas que deben estar aqui padad tener algo mas de textro auqn los demas',
          date: '2024-11-22T10:00:00Z'
        },
        {
          id: 2,
          user: {
            name: 'Jane Smith',
            username: 'janesmith',
            profileImage: 'https://via.placeholder.com/50'
          },
          content: 'This is a mock post content 2',
          date: '2023-10-02T11:00:00Z'
        },
        {
          id: 3,
          user: {
            name: 'Alice Johnson',
            username: 'alicejohnson',
            profileImage: 'https://via.placeholder.com/50'
          },
          content: 'This is a mock post content 3',
          date: '2023-10-03T12:00:00Z'
        },
        {
          id: 4,
          user: {
            name: 'Bob Brown',
            username: 'bobbrown',
            profileImage: 'https://via.placeholder.com/50'
          },
          content: 'This is a mock post content 4',
          date: '2022-10-04T13:00:00Z'
        },
        {
          id: 5,
          user: {
            name: 'Charlie Davis',
            username: 'charliedavis',
            profileImage: 'https://via.placeholder.com/50'
          },
          content: 'This is a mock post content 5',
          date: '2024-10-05T14:00:00Z'
        },
        {
          id: 6,
          user: {
            name: 'David Evans',
            username: 'davidevans',
            profileImage: 'https://via.placeholder.com/50'
          },
          content: 'This is a mock post content 6',
          date: '2024-10-06T15:00:00Z'
        },
        {
          id: 7,
          user: {
            name: 'Eva Green',
            username: 'evagreen',
            profileImage: 'https://via.placeholder.com/50'
          },
          content: 'This is a mock post content 7',
          date: '2024-10-07T16:00:00Z'
        },
        {
          id: 8,
          user: {
            name: 'Frank Harris',
            username: 'frankharris',
            profileImage: 'https://via.placeholder.com/50'
          },
          content: 'This is a mock post content 8',
          date: '2024-10-08T17:00:00Z'
        },
        {
          id: 9,
          user: {
            name: 'Grace Lee',
            username: 'gracelee',
            profileImage: 'https://via.placeholder.com/50'
          },
          content: 'This is a mock post content 9',
          date: '2024-10-09T18:00:00Z'
        },
        {
          id: 10,
          user: {
            name: 'Henry King',
            username: 'henryking',
            profileImage: 'https://via.placeholder.com/50'
          },
          content: 'This is a mock post content 10',
          date: '2024-10-10T19:00:00Z'
        }
      ]
    };
  }
};
</script>

<style scoped>
.home-container {
  width: 100%;
  height: 100%;
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