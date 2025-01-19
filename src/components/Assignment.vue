<template>
    <h4>
        In Progress Assignments
    </h4>
    <div class="tags">
        <EachTag 
        v-for="a in tags(assignments)" 
        :tag="a"  
        :key="a"
        :class="{active:tag==currentTag}"
        @click="currentTag=a"
        ></EachTag>
    </div>
    <ul>
    <each-assignment v-for="assignment in assignments" :key="assignment.id" :assignment="assignment" />
    </ul>      
</template>

<script setup>
import { computed } from "vue"
import EachAssignment from './EachAssignment.vue'
import EachTag from "./EachTag.vue"

let currentTag = "all"

const { assignments } = defineProps({
  assignments: Array,
});


function tags(lists){
    return new Set(lists.map(a => a.tag))
}
 
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
.tags {
    display: flex;
    gap: 12px;
}
</style>