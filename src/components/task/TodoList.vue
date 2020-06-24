<template>
	<ul class="todo-main">
		<TodoItem v-for="(todo,index) in todos" :key="index" :todo="todo" :index="index" :deleteItem="deleteItem"></TodoItem>
	</ul>
</template>

<script>
	import TodoItem from '@/components/task/TodoItem.vue'
	export default{
		name:"TodoList",
		data(){
			return{
				
			}
		},
		props:{
			todos:Array,
			deleteItem:Function
		},
		components:{
			TodoItem
		}
	}
</script>

<style scoped="scoped">
  .todo-main {
    margin-left: 0px;
    border: 1px solid #ddd;
    border-radius: 2px;
    padding: 0px;
	margin-top: 1rem;
	margin-bottom: 1rem;
  }

  .todo-empty {
    height: 40px;
    line-height: 40px;
    border: 1px solid #ddd;
    border-radius: 2px;
    padding-left: 5px;
    margin-top: 10px;
  }
</style>
