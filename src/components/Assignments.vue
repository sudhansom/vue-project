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
import { assignments } from '../data/data.js'

</script>

<style>

</style>