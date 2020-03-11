<template>
    <div>
        <form class="add" @submit="addTodo">
            <input class="input" v-model="title" type="text" name="title" placeholder="Add new todo..." >
            <button class="button" value="Submit" type="submit">Submit</button>
        </form>
    </div>
</template>

<script>
import uuid from 'uuid'
export default {
    name:'TodoAdd',
    data(){
        return{
            title:''
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault()
            const newTodo = {
                id:uuid.v4(),
                title:this.title,
                completed:false
            }

            this.$emit('add-todo', newTodo)
        }
    }
}
</script>

<style scoped>
    .add{
        display: flex;
    }
    .input{
        width: 100%;
        padding: 10px;
    }
    .button{
        border: none;
        background-color: teal;
        color: white;
    }
</style>