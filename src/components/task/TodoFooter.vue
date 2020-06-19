<template>
	<div>
		<input type="checkbox" v-model="checkAll"/>
		<span>已完成{{selectNumber}}/全部{{allNumber}}</span>
		<button @click="deleteSelect">清除已完成的任务</button>
	</div>
</template>

<script>
	export default{
		name:"TodoFooter",
		data(){
			return{
				
			}
		},
		props:{
			selectNumber:Number,
			allNumber:Number,
			checkAll:Boolean
		},
		methods:{
			deleteSelect(){
				
			}
		}
	}
</script>

<style scoped="scoped">
	input{
		width: 50px;
	}
	button{
		margin-left: 8.25rem;
		width: 8.25rem;
		display: inline-block;
	}
</style>
