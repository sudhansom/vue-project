<template>
  <div class="tag" 
        :class="{active:tag==modelValue}"
  >
    <span @click="emit('update:modelValue', tag)">{{ tag }}</span>
  </div>
</template>

<script setup>
defineProps({
    tag: String,
    modelValue: String
})

let emit = defineEmits(['update:modelValue'])

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