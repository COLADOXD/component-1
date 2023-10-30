<script setup>
import { ref, onMounted } from "vue";
import LoadingSpinner from "./component/LoadingSpinner.vue"
import BlogPost from "./component/BlogPost.vue";
import PaginatePost from "./component/PaginatePost.vue";

const posts = ref([]);
const postsXPage = 10
const start = ref(0);
const end = ref(postsXPage);
const loading = ref(true);

onMounted(async () => {
  loading.value = true;
  try {
    const res = await fetch("https://jsonplaceholder.typicode.com/posts");
    posts.value = await res.json();
  } catch (error) {
    console.log(error);
  } finally {
    setTimeout(() => (loading.value = false), 1500);
  }
  // fetch("https://jsonplaceholder.typicode.com/posts")
  //   .then((res) => res.json())
  //   .then((data) => (posts.value = data));
  //   .finally(() => setTimeout(() => ((loading.value = false), 1500)))
});

const favorite = ref('')

// @changeFavorite es un evento personalizado creado con el emit
// =ChangeFavorite es el nombre de la funcion a la cual se llamo 
const changeFavorites = (post) => favorite.value = post

const handlePage = (page) => {
  if (page) {
    start.value = start.value + postsXPage;
    end.value = end.value + postsXPage;
  } else if (!page) {
    start.value = start.value - postsXPage;
    end.value = end.value - postsXPage;
  }
}
</script>

<template>
  <loading-spinner v-if="loading" />
  <div v-else class="container">
    <h1>APP</h1>
    <h2>Mis Post Favoritos: {{ favorite }}</h2>

    <paginate-post :maxLength="posts.length" :end="end" :start="start" @handlePageButton="handlePage" />

    <blog-post v-for="post in posts.slice(start, end)" :key="post.id" :title="post.title" :id="post.id"
      :color="post.color" :body="post.body" @changeFavoritesName="changeFavorites" />

  </div>
</template>