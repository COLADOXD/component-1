<script setup>
import { ref } from "vue";
import BlogPost from "./component/BlogPost.vue";
import PaginatePost from "./component/PaginatePost.vue";

const posts = ref([]);

fetch("https://jsonplaceholder.typicode.com/posts")
  .then((res) => res.json())
  .then((data) => (posts.value = data))

const favorite = ref('')

// @changeFavorite es un evento personalizado creado con el emit
// =ChangeFavorite es el nombre de la funcion a la cual se llamo 
const changeFavorites = (post) => favorite.value = post
</script>

<template>
  <div class="container">
    <h1>APP</h1>
    <h2>Mis Post Favoritos: {{ favorite }}</h2>

    <paginate-post />

    <blog-post v-for="post in posts" :key="post.id" :title="post.title" :id="post.id" :color="post.color"
      :body="post.body" @changeFavoritesNombre="changeFavorites" />

  </div>
</template>