<script setup>
import {ref} from 'vue'

const task = ref([]);
const newTask = ref('');
const editMode = ref(false);

function addTask() {
    task.value.push(newTask.value);
    newTask.value = '';
}

function editTask(index) {
    newTask.value = task.value[index];
    editMode.value = true
}

function cancelEdit() {
    editMode.value = false;
}

function saveEditedTask(index) {
    task.value[index] = newTask.value;
    editMode.value = false;
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
                <!-- <button @click="addTask" class="button-addTask">+</button> -->
                <img :src="editMode ? '../../public/img/atualizar.png' : '../../public/img/mais2.png'" alt="" class="icon-buttonAdd" @click="editTask(currentIndex)">
            </div>
            <div class="list-movies">
                <ul>
                    <li v-for="(task,index) in task" :key="index">
                        <p>{{ task }}</p>
                        <img src="../../public/img/edit.png" alt="" class="icon-buttonEdit" @click="editTask(index)" >
                        <img src="../../public/img/lixo.png" alt="" class="icon-buttonDelete" @click="deleteTask(index)" >
                    </li>
                </ul>
            </div>
        </div>
        
    </div>
</template>

<style scoped>
body {overflow: hidden !important;}

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
    height: 83%;
    background-color: #2c6b74 ;
    box-shadow: 2px 2px 2px rgb(0,0,0,0.5);
    display: flex;
    flex-direction: column;
}

.field-input {
    display: flex;
    justify-content: center;
    width: 100%;
    height: 60px;
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

.list-movies {
    width: 94%;
    height: 80%;
    margin: 8px auto 0px auto;
    padding: 8px;
    overflow: auto;
    background-color: #00988d;
    border-radius: 8px;
}

.list-movies ul {
    list-style: none;
    width: 94%;
}

.list-movies ul li {
    border: 1px solid black;
    display: flex;
    justify-content: end;
    align-items: center;
    background-color: #fef5c8;
    border: none;
    border-radius: 5px;
    margin-bottom: 4px;
}

.list-movies::-webkit-scrollbar {
    width: 10px;
    height: 10px;
}

.list-movies::-webkit-scrollbar-track {
    background-color: #fef5c8;
    padding: 2px;
}

.list-movies::-webkit-scrollbar-thumb {
    border-radius: 1px;
    background-color: #013750;;
}

li  p {
    width: 86%;
    font-family: "Josefin Sans", sans-serif;
    font-size: 1.5em;
    height: 30px;
    transform: translateY(8px);
}

.button-edit {
    border: none;
}

.icon-buttonEdit, .icon-buttonDelete {
    width: 35px;
    cursor: pointer;
}

.icon-buttonAdd {
    cursor: pointer;
    width: 52px;
    height: 52px;
    transform: translateY(-3px);
}

</style>