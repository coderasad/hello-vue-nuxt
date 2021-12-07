<template>
    <div>
        <Header/>
        <div class="container">
            <div class="row justify-content-center">
                <div class="col-6 mt-5">
                    <b-list-group  v-for="(todo, index) in todos" :key="index" class="d-flex flex-row mb-2 align-items-center">
                        <b-list-group-item class="flex-grow-1">
                            {{ todo.title }}
                        </b-list-group-item>
                        <span class="btn btn-outline-primary h-100 ml-2"><NuxtLink :to="`/todos/${todo.id}/edit`">Edit</NuxtLink></span>
                    </b-list-group>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Header from "../../components/Header";
export default {
    components: {Header},
    data() {
        return {
            todos: []
        }
    },
    mounted() {
        this.$axios.get('https://jsonplaceholder.typicode.com/todos').then(({data}) => {
            this.todos = data;
        })
    }
}
</script>
