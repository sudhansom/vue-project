<template>
   <li>
            {{ assignment.title}}
            <input type="checkbox" v-model="assignment.completed"></input>
        </li>
</template>

<script setup>
defineProps({
    assignment: Object
})
</script>

<style>

</style>