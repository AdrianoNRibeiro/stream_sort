<script setup>
import {ref} from 'vue'

const task = ref([]);
const newTask = ref('');

function addTask() {
    task.value.push(newTask.value);
    newTask.value = '';
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
                <img src="../../public/img/mais2.png" alt="" class="icon-buttonAdd" @click="addTask()">
            </div>
            <div class="list-movies">
                <ul>
                    <li v-for="(task,index) in task" :key="index">
                        <p>{{ task }}</p>
                        <!-- <img src="../../public/img/lixo.png" alt="" class="icon-buttonDelete" @click="deleteTask(index)" > -->
                        <button @click="deleteTask(index)" class="buttonDelete">Excluir</button>
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
    width: 96%;
    height: 60%;
    margin: 8px auto 0px auto;
    padding: 8px;
    overflow: auto;
    background-color: #00988d;
    border-radius: 8px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.list-movies ul {
    list-style: none;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.list-movies ul li {
    border: 1px solid black;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #fef5c8;
    border: none;
    border-radius: 5px;
    margin-bottom: 4px;
    margin-right: 10px;
    width: 31%;
    height: 100px;
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
    width: 98%;
    font-family: "Josefin Sans", sans-serif;
    font-size: 1.5em;
    height: 55px;
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

.buttonDelete {
    width: 100%;
}

</style>