<template>
	<div>
		<TaskHead :addTodo="addTodo"></TaskHead>
		<TaskList :todos="todos" :deleteItem="deleteItem"></TaskList>
		<TaskFooter :allNumber="allNumber" :selectNumber="selectNumber" :checkAll="checkAll"></TaskFooter>
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
		allNumber:{
			get:function(){
				return this.todos.length
			}
		},
		selectNumber:{
			get:function(){
				const array=this.todos.filter(t => t.todoFlag===true);
				return array.length;
			}
		},
		checkAll:{
			get:function(){
				return this.allNumber==this.selectNumber
			},
			set:function(){
			}
		}
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
		}
	}
}
</script>

<style scoped="scoped">
	div{
		text-align: center;
	}
</style>
