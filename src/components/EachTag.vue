<template>
  <div class="tag">
    <span>{{ tag }}</span>
  </div>
</template>

<script setup>
defineProps({
    tag: String
})
</script>

<style>
.tag {
    border: 1px solid gray;
    padding: 2px 6px;
    border-radius: 6px;
}
</style>