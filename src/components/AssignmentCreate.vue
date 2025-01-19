<template>
    <div class="input-card">
        <input type="text">
        <button>Save</button>
    </div>
</template>

<script setup>

</script>

<style scoped>
.input-card {
    padding: 0;
    display: flex;
    justify-content: space-between;
    gap:1px;
    border-radius: 6px;
}
input {
    padding: 6px;
    height: 100%;
    flex-grow: 1;
    border-radius: 6px;

}
button {
    padding: 5px 12px;
}

</style>