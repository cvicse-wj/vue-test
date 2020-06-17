<template>
	<div>
		<TaskHead></TaskHead>
		<TaskList></TaskList>
		<TaskFooter></TaskFooter>
	</div>
</template>

<script>
	import TaskHead from '@/components/task/TodeTaskHead.vue'
	import TaskList from '@/components/task/TodeList.vue'
	import TaskFooter from '@/components/task/TaskFooter.vue'
	export default{
		name:'Task',
		data(){
			return{
				
			}
		},
		components:{
			TaskHead,
			TaskList,
			TaskFooter
		}
	}
</script>

<style>
</style>
