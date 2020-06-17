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
		commentList:[
			{
				userName:'宋阳坤',
				comment:'真的无下限'
			},
			{
				userName:'陈家俊',
				comment:'好垃圾啊！'
			},
			{
				userName:'陈冠宇',
				comment:'加班是真的严重！'
			},
			{
				userName:'景新海',
				comment:'是国家规划布局内重点软件企业、国家863成果产业化基地、中国软件研发竞争力十强企业、中国软件出口工程示范企业，拥有国家计算机信息系统集成一级资质、国家公路交通工程专业承包通信、监控、收费综合系统工程资质，通过CMMI ML5级国际认证与ISO9001国际质量体系认证'
			}
		]
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
