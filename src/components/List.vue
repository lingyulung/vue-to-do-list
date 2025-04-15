<script>
    export default {
        props: {
            list: {
                type: Array
            }
        },
        data() {
            return {
                toDoList: this.list
            }
        },
        methods: {
            complete(id) {
                const toDoItem = this.toDoList.find(item => item.id === id);

                toDoItem.completed = true;
            }
        }
    }
</script>

<template>
    <table class="toDoTable">
        <tr>
            <th>To Do</th>
            <th>When</th>
            <th>Completed</th>
            <th>Action</th>
        </tr>
        <tr v-for="item in list" :key="item.id">
            <td>{{ item.toDo }}</td>
            <td>{{ item.when }}</td>
            <td>{{ item.completed ? 'completed' : 'not completed' }}</td>
            <td><button @click="complete(item.id)">complete</button></td>
        </tr>
    </table>
</template>

<style>
    .toDoTable {
        width: 100%;
    }
    .toDoTable td,th {
        text-align: center;
    }
</style>