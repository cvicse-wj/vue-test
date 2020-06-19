<template>
	<input placeholder="请输入你的任务名称,按enter键进行确认提交!" @keyup.enter="toSubmit" v-model="todoName"/>
</template>

<script>
	export default{
		name:'TodoHead',
		data(){
			return{
				todoName:""
			}
		},
		props:{
			addTodo:Function
		},
		methods:{
			toSubmit() {
				const{todoName,addTodo} = this;
				if(!todoName) {
					alert("请输入任务内容！");
					return;
				}else{
					var obj={
						todoName:todoName,
						todoFlag:false
					};
					addTodo(obj);
					this.todoName='';
				}
			}
		}
	}
</script>

<style scoped="scoped">
	input{
		width: 19.25rem;
	}
</style>
