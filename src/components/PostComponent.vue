<template>
  <div class="post">
    <UserProfileImage :src="post.user.profileImage" />
    <div class="post-container">
      <div class="post-header">
        <div class="user-info">
          <h3>{{ post.user.name }}</h3>
          <p>@{{ post.user.username }}</p>
          <p>{{ getTimeSincePost(post.date) }}</p>
        </div>
      </div>
      <p class="post-content">{{ post.content }}</p>
      <div class="post-footer">
        <div class="footer-btns">
          <button @click="commentPost">Comment</button>
          <button @click="likePost">Like</button>
          <button @click="retweetPost">Retweet</button>
          <button @click="replyPost">Reply</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import UserProfileImage from './UserProfileImage.vue';

export default {
  name: 'PostComponent',
  components: {
    UserProfileImage
  },
  props: {
    post: {
      type: Object,
      required: true
    }
  },
  methods: {
    commentPost() {
      // Logic for commenting on the post
    },
    likePost() {
      // Logic for liking the post
    },
    retweetPost() {
      // Logic for retweeting the post
    },
    replyPost() {
      // Logic for replying to the post
    },
    getTimeSincePost(date) {
      const now = new Date();   
      const postDate = new Date(date);
      const diffInSeconds = Math.floor((now.getTime() - postDate.getTime()) / 1000);

      const minutes = Math.floor(diffInSeconds / 60);
      const hours = Math.floor(minutes / 60);
      const days = Math.floor(hours / 24);

      if (days > 0) {
        return `${days} day${days > 1 ? 's' : ''} ago`;
      } else if (hours > 0) {
        return `${hours} hour${hours > 1 ? 's' : ''} ago`;
      } else if (minutes > 0) {
        return `${minutes} minute${minutes > 1 ? 's' : ''} ago`;
      } else {
        return 'Just now';
      }
    }

  }
}
</script>

<style scoped>
.post {
  border: 1px solid #e1e8ed;
  margin: 0px 10px 10px 10px;
  border-radius: 5px;
  display: flex;
}

.post:hover {
  background-color: #f5f8fa;
  cursor: pointer;
}

.post-container {
  width: 100%;
  margin: 10px;
}

.post-header {
  display: flex;
  align-items: center;
}

.post-thread {
  margin: 10px 0px 10px 10px;
}

.profile-image {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  margin-right: 10px;
}

.user-info {
  display: flex;
  gap: 5px;
}

.user-info h3 {
  margin: 0;
  font-size: 16px;
}

.user-info p {
  margin: 0;
  color: #657786;
}

.post-content {
  text-align: left;
  margin: 10px 0;
  word-break: break-word;
}

.footer-btns {
  display: flex;
  justify-content: space-between
}

.post-footer button {
  background: none;
  border: none;
  color: #1da1f2;
  cursor: pointer;
  font: inherit;
}

.post-footer button:hover {
  text-decoration: underline;
}

button {
  margin: 0;
  padding:  0;
}
</style>