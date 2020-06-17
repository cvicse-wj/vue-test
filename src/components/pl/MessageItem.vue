<template>
	<div>
		<h3 style="margin-left: 0.3125rem;">{{comment.userName}}：</h3>
		<p style="margin-top: 0.625rem;margin-left: 1.875rem;text-indent: 5rem;">{{comment.comment}}</p>
		<div style="text-align: center;position: absolute;">
			<button @click="remove"  style="width: 50px;right: 10%;" >删除</button>
		</div>
	</div>
</template>

<script>
	export default{
		name:'MessageItem',
		props:{
			index:Number,
			comment:Object,
			deleteCommet:Function
		},
		methods:{
			remove(){
				const{index,deleteCommet} =this;
				console.log(index);
				deleteCommet(index);
			}
		}
	}
</script>

<style>
</style>
