<template>
    <div class="assignment">
        <section>
            <h4>
            {{ title }}
        </h4>
        <div class="tags">
            <EachTag 
            v-for="a in tags(assignments)" 
            :tag="a"  
            :key="a"
            v-model="currentTag"
            ></EachTag>
        </div>
        <div class="filtered" v-if="filteredAssignments().length">
        <ul>
            <each-assignment v-for="assignment in filteredAssignments()" :key="assignment.id" :assignment="assignment" />
        </ul> 
        </div>  
        <div v-else>
            <ul>
            <each-assignment v-for="assignment in assignments" :key="assignment.id" :assignment="assignment" />
        </ul> 
        </div> 
        </section>
        <slot :tag="currentTag"></slot>
    </div>  
</template>

<script setup>
import { computed, ref } from "vue"
import EachAssignment from './EachAssignment.vue'
import EachTag from "./EachTag.vue"

let currentTag = ref("all")

const { assignments } = defineProps({
  assignments: Array,
  title: String,
});

function changeTag(tag){
    currentTag.value = tag
}

function filteredAssignments(){
    if(currentTag.value==="all"){
        return assignments
    }else {
        let filtered = assignments.filter(a => a.tag == currentTag.value)
        if(filtered.length){
            return filtered
        }else {
            currentTag.value = "all"
            return assignments
        }
    }
}
function tags(lists){
    return ['all', ...new Set(lists.map(a => a.tag))]
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
.assignment {
    border: 1px solid gray;
    padding: 12px;
    border-radius: 6px;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
}
</style>