<template>
  <section>
    <header>
      <h2>
        All Assignments
      </h2>
    </header>
    <div>
      <ul>
        <li v-for="assignment in assignments" :key="assignment.id">
            {{ assignment.title}}
            <input type="checkbox" v-model="assignment.completed"></input>
        </li>
      </ul>
    </div>
  </section>
 
</template>

<script setup>
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

