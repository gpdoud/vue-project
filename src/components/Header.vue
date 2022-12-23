<script setup>
    defineProps(['name'])
</script>

<template>
    <h1 class="green">{{ name }}</h1>
</template>

<style scoped>
    .green { color: green; font-weight: bold; }
</style>