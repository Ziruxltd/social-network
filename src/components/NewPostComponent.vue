<template>
  <div class="new-post">
    <UserProfileImage src="https://via.placeholder.com/50" />
    <div class="post-container">
      <textarea v-model="newPostContent" class="post-content" ref="textAreaRef" placeholder="What's on your mind?" @input="adjustTextAreaHeight"></textarea>
      <div class="post-footer">
        <div class="footer-btns">
          <p>{{ postLengthLimit - newPostContent.length }}</p>
          <button @click="submitPost">Post</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import UserProfileImage from './UserProfileImage.vue';

const newPostContent = ref('');
const postLengthLimit = ref(280);
const textAreaRef = ref(null);

function adjustTextAreaHeight() {
  textAreaRef.value.style.height = 'auto';
  textAreaRef.value.style.height = textAreaRef.value.scrollHeight + 'px';
}

function submitPost() {
  // Logic for submitting the new post
  console.log(newPostContent.value);
  newPostContent.value = '';
}
</script>

<style scoped>
.new-post {
  border: 1px solid #e1e8ed;
  margin: 10px 10px 10px 10px;
  border-radius: 5px;
  display: flex;
}

.post-container {
  width: 100%;
  margin: 10px;
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

.post-content {
  font: inherit;
  text-align: left;
  margin: 10px 0 5px 0;
  word-break: break-word;
  width: 100%;
  height: auto;
  border: none;
  border-bottom: 1px solid #e1e8ed;
  border-radius: 5px;
  resize: none;
  outline: none;
}

.footer-btns {
  display: flex;
  justify-content: flex-end;
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
  padding: 0;
}
</style>