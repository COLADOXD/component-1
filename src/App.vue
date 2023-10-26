<script setup>
import ButtonCounter from "./component/ButtonCounter.vue"
import BlogPost from "./component/BlogPost.vue";
</script>

<template>
  <div class="container">
    <h1>APP</h1>

    <ButtonCounter />
    <button-counter />
    <blog-post title="Post 01" />
    <blog-post title="Post 02" />
    <blog-post title="Post 03" />
  </div>
</template>