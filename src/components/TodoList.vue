<template>
    <div>
        <div v-for="todo in allTodos" :key="todo.id">
        <TodoItem />
        </div>
    </div>
</template>

<script>
import TodoItem from "@/components/TodoItem.vue";
import { mapGetters } from "vuex";

export default{
    components: {
        TodoItem
    },
    computed: {
        ...mapGetters(["allTodos"])
    }

}

</script>
<style scoped>

</style>