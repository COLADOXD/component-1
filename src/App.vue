<script setup>
import { ref } from "vue";
import BlogPost from "./component/BlogPost.vue";

const posts = [
  { title: "Post 01", id: 1, description: "Lorem ipsum dolor sit amet consectetur.", color: "primary" },
  { title: "Post 02", id: 2, description: "Lorem ipsum dolor sit amet consectetur.", color: "secondary" },
  { title: "Post 03", id: 3, color: "secondary" },
]

const favorite = ref('')

// @changeFavorite es un evento personalizado creado con el emit
// =ChangeFavorite es el nombre de la funcion a la cual se llamo 
const changeFavorites = (post) => favorite.value = post
</script>

<template>
  <div class="container">
    <h1>APP</h1>
    <h2>Mis Post Favoritos: {{ favorite }}</h2>

    <blog-post v-for="post in posts" :key="post.id" :title="post.title" :id="post.id" :color="post.color"
      :description="post.description" @changeFavoritesNombre="changeFavorites" />
  </div>
</template>