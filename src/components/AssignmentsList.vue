<template>
  <section>
    <section>
        <h4>
        In Progress Assignments
      </h4>
       <ul>
       <each-assignment v-for="assignment in assignments.filter(a => !a.completed)" :key="assignment.id" :assignment="assignment" />
      </ul>
    </section>
    <section>
        <h4>
        Completed Assignments
      </h4>
      <ul>
       <each-assignment v-for="assignment in assignments.filter(a => a.completed)" :key="assignment.id" :assignment="assignment" />
      </ul>
    </section>
  </section>
 
</template>

<script setup>
import { computed } from "vue"
import EachAssignment from './EachAssignment.vue'

defineProps({
  assignments: Array
})
 
</script>

<style scoped>
ul {
    list-style-type: none;
    border: 1px solid gray;
    padding: 12px;
    border-radius: 6px;
}
li {
    display: flex;
    justify-content: space-between;
    gap: 12px;
}
</style>

