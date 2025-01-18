<template>
 <div class="assignments">
    <section>
        <section v-if="inProgress.length">
            <h4>
            In Progress Assignments
        </h4>
        <ul>
        <each-assignment v-for="assignment in inProgress" :key="assignment.id" :assignment="assignment" />
        </ul>
        </section>
        <section v-if="completed.length">
            <h4>
            Completed Assignments
        </h4>
        <ul>
        <each-assignment v-for="assignment in completed" :key="assignment.id" :assignment="assignment" />
        </ul>
        </section>
    </section>
 </div>
 
</template>

<script setup>
import { computed } from "vue"
import EachAssignment from './EachAssignment.vue'

const { assignments } = defineProps({
  assignments: Array,
});
const inProgress = computed(() => {
  return assignments.filter((a) => !a.completed);
});

const completed = computed(() => {
  return assignments.filter((a) => a.completed);
});
 
</script>

<style scoped>
ul {
    list-style-type: none;
    border: 1px solid gray;
    padding: 12px;
    border-radius: 6px;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}
li {
    display: flex;
    justify-content: space-between;
    gap: 12px;
}
.assignments {
    border: 1px solid gray;
    border-radius: 12px;
    padding: 24px 48px;
    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}
</style>

