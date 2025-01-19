<template>
<div class="assignments" v-if="assignments.length">
    <assignment v-if="inProgress.length" :assignments="inProgress"  />
    <assignment v-if="completed.length" :assignments="completed"  />
</div>
<LoadingSpinner v-else> </LoadingSpinner>
</template>

<script setup>
import { computed } from 'vue'
import Assignment from "./Assignment.vue"
import LoadingSpinner from "./LoadingSpinner.vue";
 
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
.assignments {
    border: 1px solid gray;
    border-radius: 12px;
    padding: 24px 48px;
    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}
</style>


