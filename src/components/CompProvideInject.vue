<script setup>
import { inject } from 'vue';
const fullname = inject('fullname', 'Greg');
</script>

<template>
    <div>
        <label>The name is {{ fullname }}</label>
    </div>
</template>