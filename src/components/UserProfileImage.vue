<template>
  <div class="post-thread">
    <img :src="src" alt="User Image" class="profile-image" />
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  src: {
    type: String,
    required: false,
    default: 'https://via.placeholder.com/50'
  }
});
</script>

<style scoped>
.post-thread {
  margin: 10px 0px 10px 10px;
}

.profile-image {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  margin-right: 10px;
}
</style>