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
        <div class="content-task">
            <div class="field-input">
                <input v-model="newTask" @keyup.enter="addTask" placeholder="Novo filme..." class="input-task">
                <button @click="addTask" class="button-addTask">+</button>
            </div>
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
.task-list {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    height: 100vh;
    padding: 8px;
    background-color: #fef5c8;
}

.content-task {
    border-radius: 5px;
    width: 40%;
    height: 85%;
    background-color: #00988d;
    box-shadow: 2px 2px 2px rgb(0,0,0,0.5);
    display: flex;
    flex-direction: column;
}

.field-input {
    display: flex;
    justify-content: center;
    width: 100%;
    height: 60px;
    border: 1px solid black;
    padding: 8px;
}

.input-task {
    border-radius: 5px;
    outline: none;
    border: none;
    width: 60%;
    padding: 5px;
    font-family: "Josefin Sans", sans-serif;
    font-size: 1.5em;
}

.button-addTask {
    border: none;
    background-color: #013750;
    border-radius: 0px 8px 8px 0px;
    width: 6%;
    color: #fef5c8;
    font-size: 1.8em;
    font-weight: bold;
    display: flex;
    justify-content: center;
    align-items: center;
    transform: translateX(-3px);
}

</style>