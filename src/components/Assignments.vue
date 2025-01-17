<template>
<assignments-list :assignments="assignments" />
</template>

<script setup>
// import { assignments } from '../data/data.js'
import { onMounted, ref } from 'vue'
import AssignmentsList from './AssignmentsList.vue'

let assignments = ref([])

onMounted(()=>{
  fetch("http://localhost:3002/assignments")
  .then(response => response.json())
  .then(data => {
    assignments.value = data
    console.log(data)
  })
})
</script>

<style>

</style>