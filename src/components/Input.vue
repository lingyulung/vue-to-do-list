<script>
    export default {
        emits: ['toDo'],
        data() {
            return {
                toDoItem: '',
                when: '',
                idCount: 0
            }
        },
        methods: {
            submit() {
                if (this.toDoItem) {
                    this.$emit('toDo',{
                        id: this.idCount,
                        toDo: this.toDoItem,
                        when: this.when,
                        completed: false
                    });

                    this.idCount += 1;
                }
            }
        }
    }
</script>

<template>
  <div class="inputContainer">
    <input type="text" v-model="toDoItem" />
    <input type="date" v-model="when" />
    <button @click="submit">Submit</button>
  </div>
</template>

<style>
    .inputContainer {
        padding: 2rem;
        border: 1px solid gray;
        border-radius: 15px;
        display: flex;
        flex-direction: column;
        row-gap: 0.5rem;
        column-gap: 0.5rem;
        justify-content: center;
        align-items: center;
    }
    input {
        box-sizing: border-box;
        height: 100%;
        flex: 1 1 auto;
    }
    button {
        box-sizing: border-box;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        /* padding-left: auto;
        padding-right: auto;
        padding-top: auto;
        padding-bottom: auto; */
    }
    @media only screen and (min-width: 768px) {
        .inputContainer {
            flex-direction: row;
            height: 2rem;
        }
        button {
            margin-left: 0.5rem;
        }
    } 
</style>