<template>
	<div>
		<div class="titleClass">
			<h3 class="h3Class">请发表对中创软件cvicse的看法</h3>
		</div>
		<div  style="overflow: hidden;">
			<div class="messageClass">
				<UserMessage :addComment="addComment"></UserMessage>
			</div>
			<div class="messageClass">
				<MessageList :commentList="commentList" :deleteCommet="deleteCommet"></MessageList>
			</div>
		</div>
	</div>
</template>

<script>
import UserMessage from '@/components/pl/UserMessage.vue'
import MessageList from '@/components/pl/MessageList.vue'

export default {
  name: 'message',
  data() {
	return{
		//localStorage.getItem("commetList") : 得到的字符串
		commentList:JSON.parse(window.localStorage.getItem("commentList") || '[]')
    }
  },
  components: {
	UserMessage,
	MessageList
  },
  methods:{
	deleteCommet(index){
		this.commentList.splice(index,1)
	},
	addComment(obj) {
		this.commentList.push(obj)
	}
  },
  watch:{ //监视
	commentList:{
		deep:true,
		handler:function(value){
			//将最新的值放到localstorage,注意这里需要将数组转string进行存储
			window.localStorage.setItem("commentList",JSON.stringify(value))
		}
	}
  }
}
	
</script>

<style scoped>
	.titleClass{
		height: 200px;
		background-color: rgb(235,235,235);
		overflow: hidden;
	}
	.h3Class{
		margin: 0,auto;
		font-size: 50px;
		padding-left: 30px;
		top: 35%;
		position: relative;
	}
	.messageClass{
		float: left;
		width: 45%;
	}
</style>
