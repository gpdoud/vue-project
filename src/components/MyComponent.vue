<script setup>
    import MyChildComponent from './MyChildComponent.vue';
    const props = defineProps({
        name: String, day: String, dayOfMo: Number, active: Boolean
    });
    // defineProps(['name', 'date'])
    const log = () => {
        console.log("MyComponent: Event from child");
    }
</script>

<template>
    <h1>MyComponent: {{ props.name }} on {{ props.day }} DOM: {{ props.dayOfMo }}</h1>
    <h3>MyComponent is {{  active ? "ACTIVE" : "NOT ACTIVE" }}</h3>
    <!-- <h1>MyComponent: {{ name }} on {{ date }}</h1> -->

    <MyChildComponent @child-event="log" />
</template>

<style scoped>
</style>