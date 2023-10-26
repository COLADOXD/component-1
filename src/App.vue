<script setup>
import ButtonCounter from "./component/ButtonCounter.vue"
import BlogPost from "./component/BlogPost.vue";
</script>

<template>
  <div class="container">
    <h1>APP</h1>

    <ButtonCounter />
    <button-counter />
    <blog-post title="Post 01" :id="1" description="Lorem ipsum dolor sit amet consectetur." color="primary" />
    <blog-post title="Post 02" :id="2" description="Lorem ipsum dolor sit amet consectetur." color="secondary" />
    <blog-post title="Post 03" :id="3" color="success" />
  </div>
</template>