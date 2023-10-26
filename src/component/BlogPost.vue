<script setup>

defineProps({
    title: String,
    id: Number,
    color: String,
    description: {
        type: String,
        default: "Don't have description"
    }
})

</script>

<template>
    <div class="card mt-4">
        <div class="card-body">
            <h5 class="card-tittle" :class="`text-${color}`">{{ id }}.{{ title }}</h5>
            <p>{{ description }}</p>
            <button class="btn btn-sm btn-outline-primary" @click="$emit('changeFavorites', title)">
                Mi Favorito
            </button>
        </div>

    </div>
</template>