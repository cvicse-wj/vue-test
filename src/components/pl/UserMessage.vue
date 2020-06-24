<template>
	<div class="headClass">
		用户名：<br />
		<input type="text" v-model="userName" style="width: 80%;"/>
		<br />
		<br />
		评论内容：<br />
		<textarea v-model="comment" rows="8" cols="3"  style="width: 80%;" placeholder="按enter进行提交" @keyup.enter="addMessage"></textarea>
		<br />
		<br />
		<button @click="addMessage" class="btn btn-default" style="text-align: center;width: 50px;margin-left: 73%;" >提交</button>
	</div>
</template>

<script>
export default{
	name:'UserMessage',
	props:{
		addComment:Function
	},
	data(){
		return{
			userName:'',
			comment:''
		}
	},
	methods:{
		addMessage(){
			const{userName,comment,addComment} = this;
			if(userName==='' || comment==='') {
				alert("请输入姓名或评论内容！");
				return;
			}else{
				var obj={
					userName:userName,
					comment:comment
				};
				addComment(obj);
				this.userName='';
				this.comment='';
			}
		}
	}
}
</script>

<style>
	.headClass{
		padding-top: 50px;
		padding-left: 20px;
	}
</style>
