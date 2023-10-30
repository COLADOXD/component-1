<script setup lang="ts">


const emit = defineEmits(['handlePageButton'])

</script>

<template>
    <div class="btn-group" role="group" aria-label="Basic example">
        <button type="button" class="btn btn-outline-primary" @click="emit('handlePageButton', true)">Previus</button>
        <button type="button" class="btn btn-outline-primary" @click="emit('handlePageButton', false)">Next</button>
    </div>
</template>