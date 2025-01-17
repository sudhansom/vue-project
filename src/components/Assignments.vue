<template>
  <section>
    <header>
      <h1>
        Assignments
      </h1>
    </header>
    <div>
      <ul>
        <li v-for="assignment in assignments" :key="assignment.id">{{ assignment.title}}</li>
      </ul>
    </div>
  </section>
</template>

<script setup>
const assignments = [
    {
        id: 1,
        title: "Wake up early.",
        completed: false,
    },
    {
        id: 2,
        title: "Make breakfast.",
        completed: false,
    },
    {
        id:3,
        title: "Leave for school.",
        completed: false,
    },
]

</script>

<style>

</style>