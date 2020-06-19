<template>
	<div>
		<ul>
			<TodoItem v-for="(todo,index) in todos" :key="index" :todo="todo" :index="index" :deleteItem="deleteItem"></TodoItem>
		</ul>
	</div>
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

<style>
</style>
