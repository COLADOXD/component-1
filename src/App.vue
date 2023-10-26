<script setup>
import ButtonCounter from "./component/ButtonCounter.vue"
import BlogPost from "./component/BlogPost.vue";

const posts = [
  { title: "Post 01", id: 1, description: "Lorem ipsum dolor sit amet consectetur.", color: "primary" },
  { title: "Post 02", id: 2, description: "Lorem ipsum dolor sit amet consectetur.", color: "secondary" },
  { title: "Post 03", id: 3, color: "secondary" },
]
</script>

<template>
  <div class="container">
    <h1>APP</h1>

    <ButtonCounter />
    <button-counter />
    <blog-post v-for="post in posts" :key="post.id" :title="post.title" :id="post.id" :color="post.color"
      :description="post.description" />
  </div>
</template>