<script setup>

defineProps({
    title: String,
    id: Number,
    color: String,
    body: {
        type: String,
        default: "Don't have body"
    },

})

const emits = defineEmits(['changeFavoritesName'])

</script>

<template>
    <div class="card mt-4">
        <div class="card-body">
            <h5 class="card-tittle" :class="`text-${color}`">{{ id }}.{{ title }}</h5>
            <p>{{ body }}</p>
            <button class="btn btn-sm btn-outline-primary" @click="emits('changeFavoritesName', title)">
                Mi Favorito
            </button>
        </div>

    </div>
</template>