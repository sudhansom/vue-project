<template>
  <div class="tag" 
        :class="{active:tag==currentTag}"
  >
    <span @click="emit('changeTag', tag)">{{ tag }}</span>
  </div>
</template>

<script setup>
defineProps({
    tag: String,
    currentTag: String
})

let emit = defineEmits(['changeTag'])

</script>

<style>
.tag {
    border: 1px solid gray;
    padding: 2px 6px;
    border-radius: 6px;
}
.active {
    border-color: rgb(87, 152, 217);
}
</style>