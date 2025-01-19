<template>
    <div class="input-card">
        <input type="text" v-model="task">
        <button @click="saveTask">Save</button>
    </div>
</template>

<script setup>
import { ref } from "vue"

let task = ref("")

async function saveTask(){
    let data = {
        id:44,
        title: task.value,
        completed: false,
        tag: 'tag'
    }
    try{
        const response = await fetch("http://localhost:3002/assignments", {
            method: 'POST',
            headers:{
                'Content-Type': 'application/json',
            },
            body: JSON.stringify(data)
        })
        if(response.ok){
            console.log('Task Saved', data)
        }else {
            throw new Error('Not Saved')
        }
    }catch(err){
        console.log("Serious Error occured", err)
    }
}

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