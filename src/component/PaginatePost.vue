<script setup lang="ts">

const props = defineProps({
    start: {
        type: Number,
    }
})

const emit = defineEmits(['handlePageButton'])

</script>

<template>
    <div class="btn-group" role="group" aria-label="Basic example">
        <button :disabled="props.start === 0" type="button" class="btn btn-outline-primary"
            @click="emit('handlePageButton', false)">Previus</button>
        <button type="button" class="btn btn-outline-primary" @click="emit('handlePageButton', true)">Next</button>
    </div>
</template>