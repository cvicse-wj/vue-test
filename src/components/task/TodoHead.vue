<template>
	<input placeholder="请输入你的任务名称,按enter键进行确认提交!" @keyup.enter="toSubmit" v-model="todo"/>
</template>

<script>
	export default{
		name:'TodoHead',
		data(){
			return{
				todo:""
			}
		},
		props:{
			todos:Array
		},
		methods:{
			toSubmit() {
				this.todos.push(this.todo)
			}
		}
	}
</script>

<style>
</style>
