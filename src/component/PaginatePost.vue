<script setup>

const props = defineProps({
    start: {
        type: Number,
    },
    end: {
        type: Number,
    },
    maxLength: {
        type: Number,
    }
})

const emit = defineEmits(['handlePageButton'])

</script>

<template>
    <div class="btn-group" role="group" aria-label="Basic example">
        <button :disabled="props.start <= 0" type="button" class="btn btn-outline-primary"
            @click="emit('handlePageButton', false)">Previus </button>
        <button :disabled="props.end >= props.maxLength" type="button" class="btn btn-outline-primary"
            @click="emit('handlePageButton', true)">Next</button>
    </div>
</template>