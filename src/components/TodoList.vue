<script>

export default {
    data() {
        return {
            newTodo: '',
            todos: [
                {
                    title: 'Покормить кота',
                    isDone: false,
                },
                {
                    title: 'Погулять с собакой',
                    isDone: false,
                },
                {
                    title: 'Сделать ДЗ',
                    isDone: true,
                }
            ]
        }
    },

    methods: {
        add(){
            if(!this.newTodo){
                return;
            }
            this.todos.push({
                    title: this.newTodo,
                    isDone: false
            })
            this.newTodo = ''
        },
        remove(index){
            this.todos.splice(index, 1)
        }
    }
}
</script>

<template>
    <div class="todo-list">
        <div class="input-group mb-3">
            <input  
            v-model="newTodo"
            type="text"
                    class="form-control">

            <button
            @click="add"
            class="btn btn-outline-secondary"
                    type="button">
                    Добавить
            </button>
        </div>

        <ul class="list-group">

            <!-- Вёрстка одной тудушки -->
            <li v-for="(item, index) in todos"
            class="list-group-item"
            :class="{
                done: item.isDone
            }"
            >
                <div class="input-group">
                    <div class="input-group-text">
                        <input
                        v-model="item.isDone"
                        class="form-check-input mt-0"
                                type="checkbox">
                    </div>
                    <span class="input-group-text todo-title">
                        {{item.title}}
                    </span>
                    <button 
                    @click="remove(index)"
                    class="btn btn-outline-secondary"
                            type="button">
                        X
                    </button>
                </div>
            </li>
            <!-- Конец вёрстки -->
            
        </ul>
    </div>
</template>

<style>
.todo-title {
    flex: 1;
}
.input-group {
    cursor: pointer;
}
.done .todo-title {
    text-decoration: line-through;
}
</style>