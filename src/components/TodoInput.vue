<template>
    <div>
        <div class="row">
         <input @change="todoTextChange" v-bind:value="todoText" class="col form-control mr-2" type="text" />
         <button @click="addTodo1" class="btn btn-primary">Add</button>
        </div>
    </div>
</template>

<script>
import { mapActions} from 'vuex';
import { v1 } from 'uuid';

export default {
    data() {
        return {
            todoText: ""

        }
    },
    methods: {
        ...mapActions(["addTodo"]),
        todoTextChange(e) {
            this.todoText = e.target.value
        },

        addTodo1() {
            this.addTodo({
                id: v1(),
                tittle: this.todoText
            });
            this.todoText = "";
        }
    }

};

</script>
<style scoped>

</style>

