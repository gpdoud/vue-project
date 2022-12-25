<script setup>
    defineEmits(['child-event'])
</script>

<template>
    <h4>MyChildComponent</h4>
    <button @click="$emit('child-event')">Emit Event</button>
</template>

<style scoped></style>