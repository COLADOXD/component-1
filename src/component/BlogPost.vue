<script setup>

defineProps(['title', 'id', 'description', 'color'])

</script>

<template>
    <div class="card mt-4">
        <div class="card-body">
            <h5 class="card-tittle" :class="`text-${color}`">{{ id }}.{{ title }}</h5>
            {{ description }}
        </div>
    </div>
</template>