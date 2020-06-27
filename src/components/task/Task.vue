<template>
  <div class="todo-container">
	<div class="todo-wrap">
		<TaskHead :addTodo="addTodo"></TaskHead>
		<TaskList :todos="todos" :deleteItem="deleteItem"></TaskList>
		<TaskFooter  :todos="todos" :selectAll="selectAll" :deleteSelItem="deleteSelItem"></TaskFooter>
	</div>
  </div>
</template>

<script>
import TaskHead from '@/components/task/TodoHead.vue'
import TaskList from '@/components/task/TodoList.vue'
import TaskFooter from '@/components/task/TodoFooter.vue'
export default{
	name:'Task',
	data(){
		return{
			todos:JSON.parse(localStorage.getItem("todos") || "[]")
		}
	},
	components:{
		TaskHead,
		TaskList,
		TaskFooter
	},
	computed:{
	
	},
	watch:{
		todos:{
			deep:true,
			handler:function(value){
				localStorage.setItem("todos",JSON.stringify(value))
			}
		}
	},
	methods:{
		addTodo:function(todo){
			this.todos.push(todo)
		},
		deleteItem:function(index){
			this.todos.splice(index,1)
		},
		deleteSelItem:function(){
			this.todos=this.todos.filter(todo=>!todo.todoFlag)
		},
		selectAll:function(value){
			this.todos.forEach(todo => {
				todo.todoFlag=value
			})
		}
	}
}
</script>

<style scoped="scoped">
  .todo-container {
	width: 600px;
	margin: 0 auto;
  }
  .todo-container .todo-wrap {
	padding: 10px;
	border: 1px solid #ddd;
	border-radius: 5px;
  }
</style>
