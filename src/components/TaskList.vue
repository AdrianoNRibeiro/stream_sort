<script setup>
import {ref} from 'vue'

const task = ref([]);
const newTask = ref('');

function addTask() {
    task.value.push(newTask.value);
    newTask.value = '';
}

function editTask(index) {

}

function deleteTask(index) {
    task.value.splice(index, 1);
}
</script>

<template>
    <div class="task-list">
        <div class="content-task" style="border: 1px solid red; width: 60%; height: 50vh;">
            <input v-model="newTask" @keyup.enter="addTask" placeholder="Nova tarefa...">
            <button @click="addTask">Adicionar</button>
            <ul>
                <li v-for="(task,index) in task" :key="index">
                    {{ task }}
                    <button @click="editTask(index)">Editar</button>
                    <button @click="deleteTask(index)">Excluir</button>
                </li>
            </ul>
        </div>
        
    </div>
</template>

<style scoped>

</style>